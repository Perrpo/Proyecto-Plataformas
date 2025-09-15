<template>
  <div class="notifications-panel">
    <h2>Panel de Notificaciones</h2>
    <ul>
      <li v-for="notification in notifications" :key="notification.id">
        {{ notification.message }} - <span>{{ notification.date }}</span>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'NotificationsPanel',
  setup() {
    const notifications = ref([
      { id: 1, message: 'Producto A está a punto de vencer.', date: '2023-10-01' },
      { id: 2, message: 'Producto B ha sido donado.', date: '2023-10-02' },
      { id: 3, message: 'Descuento aplicado a Producto C.', date: '2023-10-03' },
    ]);

    return {
      notifications,
    };
  },
});
</script>

<style scoped>
.notifications-panel {
  border: 1px solid #ccc;
  padding: 16px;
  border-radius: 8px;
  background-color: #f9f9f9;
}

.notifications-panel h2 {
  margin-bottom: 12px;
}

.notifications-panel ul {
  list-style-type: none;
  padding: 0;
}

.notifications-panel li {
  margin: 8px 0;
}
</style>