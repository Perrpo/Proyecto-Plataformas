<template>
  <button @click="applyDiscount" class="discount-button">
    Apply Discount
  </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'DiscountButton',
  props: {
    productId: {
      type: String,
      required: true
    },
    discountAmount: {
      type: Number,
      required: true
    }
  },
  methods: {
    async applyDiscount() {
      try {
        const response = await fetch(`/api/products/${this.productId}/discount`, {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify({ discount: this.discountAmount })
        });

        if (!response.ok) {
          throw new Error('Failed to apply discount');
        }

        const data = await response.json();
        alert(`Discount applied: ${data.message}`);
      } catch (error) {
        console.error(error);
        alert('Error applying discount');
      }
    }
  }
});
</script>

<style scoped>
.discount-button {
  background-color: #4CAF50;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.discount-button:hover {
  background-color: #45a049;
}
</style>