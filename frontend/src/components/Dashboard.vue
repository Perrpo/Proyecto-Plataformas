<template>
  <div class="dashboard">
    <h1>Dashboard</h1>
    <ProductList />
    <div class="actions">
      <DonateButton />
      <DiscountButton />
    </div>
    <MapView />
    <NotificationsPanel />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import ProductList from './ProductList.vue';
import DonateButton from './DonateButton.vue';
import DiscountButton from './DiscountButton.vue';
import MapView from './MapView.vue';
import NotificationsPanel from './NotificationsPanel.vue';

export default defineComponent({
  name: 'Dashboard',
  components: {
    ProductList,
    DonateButton,
    DiscountButton,
    MapView,
    NotificationsPanel,
  },
});
</script>

<style scoped>
.dashboard {
  padding: 20px;
}

.actions {
  margin: 20px 0;
}
</style>