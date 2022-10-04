<template>
  <div class="container my-5">
    <div class="row">
      <div class="col-12 col-md-5 offset-md-1 imgProduct">
        <img class="rounded-3" :src="'http://localhost:8000/storage'+product.image.substring(6)" >
      </div>
      <div class="col-12 col-md-5 align-self-center">
        <h1 class="text-center mb-4">{{product.name}}</h1>
        <p class="text-center">{{product.description}}</p>
        <div class="text-center fs-1 fw-bold">
          {{product.price}}
          <i class="fa fa-euro"></i>
        </div>
        <div class="text-center">
          <a v-on:click="addToCart" ><i class="fa fa-heart fa-3x text-danger"></i></a>
        </div>
        <div class="text-center" :class="[inserted==true ?'text-danger' : 'text-success']">
          {{this.message}}
        </div>
      </div>
    </div>
    <modal :cart="cart"/>
  </div>
</template>

<script>
import Modal from "~/components/Modal";
export default {
  name: "Product",
  components:{
    Modal
  },
  data(){
    return{
      cart:[],
      inserted:false,
      message:''
    }
  },
  mounted() {
    this.cart=JSON.parse(localStorage.getItem('cart-storage')||'[]')
    console.log(this.cart)
  },
  props: {
    product: Object,

  },
  methods:{
    addToCart(){
      console.log(this.cart)
      for (let item in this.cart){
        if(this.cart[item].id===this.product.id){
          this.inserted=true
          break
        }else{
          this.inserted=false
        }
      } // repeating code 
      if(this.inserted===false){
        this.cart.push({
          id:this.product.id,
          name:this.product.name,
          description:this.product.description,
          price:this.product.price,
          image:this.product.image
        }) 
        this.message="Added to your cart"
      }else{
        this.message="You have already added"
      }
      localStorage.setItem('cart-storage',JSON.stringify(this.cart));
    }
  }
}
</script>

<style scoped>
.fa:hover {
  color: dodgerblue !important;
}
.imgProduct:hover img{
  transform: scale(1.2);
}

.imgProduct img {
  transition: 0.5s all ease-in-out;
}
</style>
