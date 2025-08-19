<template>
  <button @click="donate" class="donate-button">
    Donar
  </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'DonateButton',
  methods: {
    donate() {
      // Logic to handle donation process
      console.log('Donation process initiated');
      // Here you would typically make an API call to the backend
    }
  }
});
</script>

<style scoped>
.donate-button {
  background-color: #4CAF50; /* Green */
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}

.donate-button:hover {
  background-color: #45a049;
}
</style>