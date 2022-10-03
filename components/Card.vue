<template>
  <div>
    <div class="card shadow p-2 mb-3 bg-body rounded position-relative container" style="width: 18rem;">
        <div class="imgDiv">
          <a :href="'Product?id='+String(product.id)">
            <img :src="'http://localhost:8000/storage'+product.image.substring(6)" class="card-img-top" height="270"
                 :alt="product.name">
          </a>
        </div>
      <a v-on:click="addToCart" class="position-absolute end-0 margin-285"><i class="fa fa-heart fa-3x text-danger"></i></a>

      <div class="card-body">
        <h5 class="card-title text-center">{{ product.name }}</h5>
        <p class="card-text text-center">{{ product.price }} <i class="fa-euro fa"></i></p>


        <div class="text-center ">
          <a :href="'Product?id='+String(product.id)" class="btn btn-secondary text-white px-4">
            Open
          </a>
        </div>
        <div class="text-center" :class="[inserted==true ?'text-danger' : 'text-success']">
          {{ this.message }}
        </div>

      </div>
    </div>


  </div>

</template>

<script>

export default {
  name: "Card",
  props: {
    product: Object,
    cart: Array,
  },
  data() {
    return {
      inserted: false,
      message: ''
    }
  },

  methods: {
    addToCart() {
      console.log(this.cart)
      for (let item in this.cart) {
        if (this.cart[item].id === this.product.id) {
          this.inserted = true
          break
        } else {
          this.inserted = false
        }
      }
      if (this.inserted === false) {
        this.cart.push({
          id: this.product.id,
          name: this.product.name,
          description: this.product.description,
          price: this.product.price,
          image: this.product.image
        })
        this.message = "Added to your cart"
      } else {
        this.message = "You have already added"
      }
      localStorage.setItem('cart-storage', JSON.stringify(this.cart));
    }
  }
}
</script>

<style scoped>
.fa:hover {
  color: dodgerblue !important;
}

.margin-285 {
  margin-top: 285px;
}

.imgDiv:hover img {
  transform: scale(1.3);
}

.imgDiv img {
  width: 100%;
  transition: 0.5s all ease-in-out;
}

.imgDiv {
  width: 270px;
  height: 300px;
  overflow: hidden;
  margin: 0 auto;
}
</style>
