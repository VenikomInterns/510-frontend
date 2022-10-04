<template>
  <div>
    <product :product="product"/>
  </div>
</template>

<script>
import Product from "~/components/Product";


export default {
  name: "Show",
  components:{
      Product
  },
  data(){
    return{
      product:[],
      product_id:this.$route.query.id
    }
  },
  async fetch() {
    const response = await fetch(
      "http://127.0.0.1:8000/api/products/" +this.product_id
    ).then(res => res.json()); 
    this.product = response //ok
  },
}
</script>

<style scoped>

</style>
