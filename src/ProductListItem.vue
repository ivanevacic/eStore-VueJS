<template>
  <li>
    <img :src="product.image">
    <p><strong>{{ product.name }}</strong></p>
    <p><strong>{{ product.description }}</strong> <a @click="requestRemoval">Hide this item</a></p>
  </li>
</template>

<script>
  // Exports the object that defines this component
  export default {
    name: 'product-list-item',
    props: ['product'],
    methods: {
      requestRemoval() {
        this.$emit('remove');
      }
    }
  };
</script>

<!-- 'scoped' -> This SCSS is only applied to elements of this component -->
<style lang="scss" scoped>
  img {
    float: left;
    width: 300px;
  }
  li {
    margin-bottom: 40px;
    clear: both;
  }
</style>


