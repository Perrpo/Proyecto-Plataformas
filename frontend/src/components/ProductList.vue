<template>
  <div class="product-list">
    <h2>Productos Próximos a Vencer</h2>
    <ul>
      <li v-for="product in products" :key="product.id">
        <span>{{ product.name }} - Vence el: {{ product.expirationDate }}</span>
        <div>
          <DonateButton :product="product" />
          <DiscountButton :product="product" />
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import DonateButton from './DonateButton.vue';
import DiscountButton from './DiscountButton.vue';

export default defineComponent({
  name: 'ProductList',
  components: {
    DonateButton,
    DiscountButton
  },
  data() {
    return {
      products: [] as Array<{ id: number; name: string; expirationDate: string }>
    };
  },
  mounted() {
    this.fetchProducts();
  },
  methods: {
    async fetchProducts() {
      try {
        const response = await fetch('/api/products'); // Adjust the API endpoint as necessary
        this.products = await response.json();
      } catch (error) {
        console.error('Error fetching products:', error);
      }
    }
  }
});
</script>

<style scoped>
.product-list {
  padding: 20px;
}

.product-list h2 {
  margin-bottom: 10px;
}

.product-list ul {
  list-style-type: none;
  padding: 0;
}

.product-list li {
  margin-bottom: 15px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>