<template>
  <div>
    <h2><strong>{{product.name}}</strong></h2>
    <router-link to="/products">Back to all products</router-link>
    <img :src="product.image">
    <p><strong>{{ product.description }}</strong></p>
    <strong>{{product.price}}</strong>
    <div>
      <button>Add to cart</button>
    </div>
  </div>
</template>

<script>
  // Exports the object that defines this component
  export default {
    name: 'product',
    data() {
      return {
        product: {}
      }
    },
    created(){
      let id = this.$route.params.id;
      $.getJSON(`https://hplussport.com/api/products/id/${id}`)
        .done(data => {this.product = data;})
    }    
  };
</script>

<!-- 'scoped' -> This SCSS is only applied to elements of this component -->
<style lang="scss" scoped>
  img {
    width: 700px;
    height: 700px;
  }

</style>


