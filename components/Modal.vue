<template>

  <!-- Modal -->
  <div class="modal fade "  id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog ">
      <div class="modal-content modal-width-700px">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">Your cart</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body modal-width-600px ">
          <table class="table">
            <thead>
              <tr>
                <th>
                  Name
                </th>
                <th>
                  Description
                </th>
                <th>
                  Price
                </th>
                <th>
                  Image
                </th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="product in cart">
                <td>
                  {{product.name}}
                </td>
                <td>
                  {{product.description}}
                </td>
                <td>
                  {{product.price}}&#8364;
                </td>
                <td>
                  <img :src="'http://localhost:8000/storage'+product.image.substring(6)"  height="100">
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
          <button type="button" class="btn btn-primary">Save changes</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props:{
    cart:Array
  }
}
</script>

<style scoped>
.modal-width-700px{
  width: 700px !important;
}

</style>
