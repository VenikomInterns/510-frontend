<template>
    <div>
      <nav class="container navbar-expand-lg navbar bg-primary text-dark position-relative">
        <a href="/"><img height="75" src="~/assets/images/logo/online-shop.png"></a>
        <div class="container">

          <a class="navbar-brand fs-2" href="/">Online Shop</a>
          <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
                  aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav">
              <li class="nav-item ms-4 px-1 fs-5" v-for="link in links">
                <a class="nav-link active" aria-current="page" :href="link.link">{{link.name}}</a>
              </li>
            </ul>
          </div>
        </div>
        <button type="button" class="btn position-absolute end-0" data-bs-toggle="modal" data-bs-target="#exampleModal">
          <i class="fa fa-shopping-cart text-secondary fa-3x"></i>
        </button>
      </nav>

    </div>
</template>

<script>
export default {
  name: "CustomNavbar",
  data(){
    return{
      links:[
        {
          name:'Products',
          link:'/products',
        },
        {
          name:'About us',
          link:'/',
        },
        {
          name:'Contact',
          link:'/',
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>
