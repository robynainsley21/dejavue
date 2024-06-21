<template>
  <h1 class="mt-5">Products</h1>
  <CardComp class="mx-auto mb-4" v-for="product in products" :key="product.id">
    <template #cardHeader>
      <img class="img-fluid" :src="product.img_url" :alt="product.productName" loading="lazy">
    </template>
    <template #cardBody>
      <p>{{ product.productName }}</p>
      <p>R{{ product.price }}</p>
      <p>{{ product.description }}</p>
      <p :class="{
          inStock: product.status.toLowerCase() == 'in-stock',
          outOfStock: product.status.toLowerCase() == 'out-of-stock'
      }">{{ product.status }}</p>
    </template>
  </CardComp>
</template>

<script>
import CardComp from '@/components/CardComp.vue';

export default {
  name: 'ProductsComp',
  data() {
    return {
      products: [
        {
          id: 1,
          img_url: 'https://robynainsley21.github.io/images/ecommerce-skincare/acne-treatment-set.jpg',
          productName: 'Acne Set',
          price: 459,
          status: 'Out-of-stock',
          description: 'Reduces the appearance of fine lines, improves skin elasticity, and helps to reduce the appearance of pores.'
        },
        {
          id: 2,
          img_url: 'https://robynainsley21.github.io/images/ecommerce-skincare/Daily Microfoliant.jpg',
          productName: 'Microfoliant',
          price: 150,
          status: 'In-stock',
          description: 'The inclusion of oatmeal allows to soothe and calm irritated skin.'
        }, {
          id: 3,
          img_url: 'https://robynainsley21.github.io/images/ecommerce-skincare/avo-eye-cream.jpg',
          productName: 'Eye Cream',
          price: 109,
          status: 'In-stock',
          description: 'Helps to address dark circles, puffiness, and fine lines around the delicate eye area.'
        }, {
          id: 4,
          img_url: 'https://robynainsley21.github.io/images/ecommerce-skincare/cleansing-set.jpg',
          productName: 'Cleansing Set',
          price: 459,
          status: 'In-stock',
          description: 'Get clear, radiant skin with the powerful formula and combination of this treatment set.'
        }, {
          id: 5,
          img_url: 'https://robynainsley21.github.io/images/ecommerce-skincare/day-cream.jpg',
          productName: 'Day Cream',
          price: 89,
          status: 'Out-of-stock',
          description: 'A combination of ingredients that help to repair and restore the skin.'
        },
      ]
    }
  },
  components: {
    CardComp
  }
}
</script>

<style>
.image {
  width: 7rem;
}

.inStock{
  border: 2px solid green;
}

.outOfStock{
  border: 2px solid red;
}
</style>