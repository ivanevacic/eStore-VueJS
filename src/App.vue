<template>
  <product-list :products="theProducts" title="Shop our award-winning product line"></product-list>  
</template>

<script>
import ProductList from './ProductList.vue'

export default {
  name: 'app',
  // In component,data must be a function that returns
  data() {
    return {
      theProducts: []
    };
  },
  components : {
    'product-list': ProductList
  },
  created (){
    $.getJSON('https://hplussport.com/api/products')
     .done(data => {this.theProducts = data;});
  }
}
</script>
