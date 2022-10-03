<template>
  <section class="container my-3">

    <div class="row text-center">
      <div class="col-12 col-md-4 " v-for="cart in carts">
        <div>
          <i :class="cart.icon+ ' fa fa-5x text-secondary'" ></i>
        </div>
        <div class="fw-bold my-3">
          {{ cart.name }}
        </div>
        <div class="px-5">
          {{ cart.text }}
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "FeaturedServices",
  data() {
    return {
      carts: [
        {
          icon: 'fa-laptop',
          name: 'lorem ipsum',
          text: 'In publishing and graphic design, Lorem ipsum is a placeholder text ' +
            'commonly used to demonstrate the visual form of a document or a' +
            ' typeface without relying on meaningful content.'
        },
        {
          icon: 'fa-briefcase',
          name: 'test',
          text: 'In publishing and graphic design, Lorem ipsum is a placeholder text ' +
            'commonly used to demonstrate the visual form of a document or a' +
            ' typeface without relying on meaningful content.'
        },
        {
          icon: 'fa-building-o',
          name: 'test',
          text: 'In publishing and graphic design, Lorem ipsum is a placeholder text ' +
            'commonly used to demonstrate the visual form of a document or a' +
            ' typeface without relying on meaningful content.'
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>
