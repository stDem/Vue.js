<template>
  <div v-for="product in products" :key="product.id">
    <p>Название: {{ product.name }}</p>
    <p>Цена: {{ formattedPrice(product.price) }}</p>  
    <p v-if="product.available === true">Available</p>
    <p v-else>Out of stock</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        { id: 1, name: "Хлеб", price: 50, available: true },
        { id: 2, name: "Молоко", price: 75, available: false },
        { id: 3, name: "Соль", price: 20, available: true },
        { id: 4, name: "Сахар", price: 63, available: false },
      ],
    };
  },
  computed: {
      formattedPrice(price) {
        let formattedNumber = price.toLocaleString('en-US', {style: 'currency', currency: 'USD'});
          return formattedNumber;
        //   return `$ ${price}`;
        
      
    },
  },
};
</script>

<style lang="scss" scoped></style>
