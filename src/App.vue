<template>
  <router-view :products="theProducts" title="Shop our award-winning product line"></router-view> 
</template>

<script>


export default {
  name: 'app',
  // In component,data must be a function that returns
  data() {
    return {
      theProducts: []
    };
  },
  created (){
    $.getJSON('https://hplussport.com/api/products')
     .done(data => {this.theProducts = data;});
  }
}
</script>
