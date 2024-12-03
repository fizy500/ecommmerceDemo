<script>
export default {
  props: {
    item: {
      type: Object,
      required: true
    }
  }
};
</script>

<template>
  <div class="product-card">
    <img :src="item.image" :alt="item.name" class="product-image" />
    <h3>{{ $t('product_title') }}: {{ item.name }}</h3>
    <p>{{ $t('product_price') }}: ${{ item.price }}</p>
    <p>{{ $t('product_description') }}: {{ item.description }}</p>
    <button class="product-button">{{ $t('add_to_cart') }}</button>
  </div>
</template>


<style scoped>
.product-card {
  border: 1px solid #ddd;
  background-color: bisque;
  padding: 16px;
  margin: 8px;
  border-radius: 8px;
  text-align: center;
}

.product-image {
  max-width: 100%;
  height: auto;
  margin-bottom: 16px;
}





.product-button {
  border: 1px solid blueviolet;
  border-radius: 8px;
  padding:5px;
}
</style>