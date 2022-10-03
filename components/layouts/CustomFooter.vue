<template>
  <footer class="bg-primary py-4 border-top">
    <div class="container">
      <div class="row">
        <div class="col-12 col-md-5 text-center text-md-start">
          <img src="~/assets/images/logo/online-shop.png" height="130">
        </div>
        <div class="col-12 text-center text-md-start col-md-2  offset-md-5 ">
          <div class="pt-2" v-for="(link,i) in links" :key="i">
            <a class="text-decoration-none text-dark"  :href="link.link">{{link.name}}</a>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "CustomFooter",
  data(){
    return{
      links:[
        {
          name: 'Home',
          link: '/'
        },
        {
          name: 'Products',
          link: '/products'
        },
        {
          name: 'About us',
          link: '/'
        },
        {
          name: 'Contact',
          link: '/'
        }

      ]
    }
  }
}
</script>

<style scoped>

</style>
