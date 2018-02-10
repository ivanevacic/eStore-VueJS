<template>
  <div class="product-list">
    <h2> {{ title }} </h2>
      <ul>
        <product-list-item @remove="remove(i)" v-for="(product, i) in products" :product="product" :key="product.id">
         </product-list-item>
      </ul>
  </div>
</template>

<script>
  // Import ProductsListItem nad register it as local child component
  import ProductsListItem from './ProductListItem.vue';

  export default {
    name: 'product-list',
    props: ['products', 'title'],
    // Child component
    components: {
      'product-list-item': ProductsListItem
    },
    methods: {
      remove(i) {
        this.products.splice(i, 1);
      }
    }
  }
</script>

<!-- 'scoped' -> This SCSS is only applied to elements of this component -->
<style lang="scss" scoped>
  h2 {
    margin-bottom: 40px;
  }
  ul {
    list-style-type: none;
  }
</style>

