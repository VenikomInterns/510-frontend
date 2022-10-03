<template>
  <section>
    <div id="carouselExampleControls" class="carousel slide max-width-1800 mx-auto h-100 " data-bs-ride="carousel">
      <div class="carousel-inner">
        <div class="carousel-item" :class="[i === 0 ? 'active' : '']" v-for="(pic,i) in pictures" :key="i">
          <NuxtLink :to = pic.link  class="ratio ratio-4x10">
            <img :src="pic.img" class="d-block w-100" alt="...">
            <div class="carousel-caption  bottom-0 margin-top-17">
              <h1 style="font-size: 4rem;font-family: 'Comic Sans MS'" class="fw-bolder text-white">Shop online</h1>

            </div>
          </NuxtLink>
        </div>
      </div>
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleControls"
              data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleControls"
              data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
  </section>
</template>

<script>
export default {
  name: "Carousel",
  data() {
    return {
      pictures: [
        {
          img: require('assets/images/Carousel/shop1.webp'),
          link: '/'
        },
        {
          img: require('assets/images/Carousel/shop2.jpg'),
          link: '/'
        }
      ]
    }
  }

}
</script>

<style scoped>
.max-width-1800{
  max-width: 1800px;
}
.margin-top-17{
  margin-top: 17%;
}

</style>
