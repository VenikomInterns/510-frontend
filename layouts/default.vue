<template>
<div>
  <custom-navbar class="bg-primary border-bottom"/>
  <nuxt/>
  <custom-footer/>
</div>
</template>

<script>
import CustomNavbar from "~/components/layouts/CustomNavbar";
import CustomFooter from "~/components/layouts/CustomFooter";
export default {
  name: "default",
  components:{
    CustomFooter,CustomNavbar
  }
}
</script>

<style scoped>

</style>
