<template>
  <div class="product"  v-for="product in products" >
      <div class="product-inner" >
          <div class="product-wrap-text">
              <h2 class="bg-text" >asdasdasds</h2>
          </div>
            <div class="product-image-wrap">
                <img :src="product.src" class="image"/>
            </div>
              <div class="product-details">
                <router-link to="/drivings">
                <h2 >{{product.title}}</h2>
                </router-link>
                <p>
                  {{product.description}}
                </p>
              </div>
      </div>
  </div>
</template>

<script>
import Home from "@/components/Home";
export default {
  name: 'product',
  props: ['product'],
  component: {Home}
}
</script>

<style>


</style>




