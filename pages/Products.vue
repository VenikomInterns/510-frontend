<template>
  <div class="container my-4">
    <h1 class="text-center">Products</h1>
    <select id='select' v-on:change="changeItem( $event)" class="select col-3 btn btn-secondary text-lg-start mb-4 text-white ">
      <option class=" " id="category" v-for="category in categories" :key="category.id" :value="category.id">
        {{category.name}}
      </option>
    </select>
    <div class="row">
      <div class="col-12 col-lg-3 col-md-4 justify-content-center d-flex":key="product.id" v-for="product in products">
        <card :product="product" :cart="cart"/>
      </div>
    </div>

    <modal :cart="cart"/>
  </div>
</template>

<script>
import Card from "~/components/Card";
import Modal from "~/components/Modal";

export default {
  name: "Products",
  data() {
    return {
      categories: [],
      products:[],
      cart:[],
    }
  },

  components:{
    Card,Modal
  },
  async fetch() {
    const response = await fetch(
      'http://127.0.0.1:8000/api/categories'
    ).then(res => res.json());
    this.categories = response.data;
    let category_id=this.categories[0].id
    const response1 = await fetch(
      'http://127.0.0.1:8000/api/category/'+category_id
    ).then(res => res.json());
    this.products=response1.data 

  },
  mounted() {
    this.cart=JSON.parse(localStorage.getItem('cart-storage')||'[]')
  }
  ,
  methods:{
    async changeItem(event) {
      let id = document.getElementById("select").value
      const response = await fetch(
        'http://127.0.0.1:8000/api/category/'+id
      ).then(res => res.json());
      this.products=response.data
    },
  },


}
</script>

<style scoped>

</style>
