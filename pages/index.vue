<template>
  <div>
    <carousel/>
    <div class="py-4 text-center">
      <h1 class="text-secondary">Shop online from everywhere</h1>
    </div>
    <featured-services/>
    <modal :cart="cart"/>
  </div>
</template>

<script>
import FeaturedServices from "~/components/FeaturedServices";
import Carousel from "~/components/Carousel";
import Modal from "~/components/Modal"

export default {
  name: 'IndexPage',
  components: {
    Carousel, Modal, FeaturedServices
  },
  data() {
    return {
      cart: [],
    }
  },
  mounted() {
    this.cart = JSON.parse(localStorage.getItem('cart-storage') || '[]')
    console.log(this.cart)
  },
}
</script>
