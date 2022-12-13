<script setup>
defineProps({
  user: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <div class="user">
    <div class="info">
      {{ user.first_name }} {{ user.last_name }}<br />
      {{ user.email }}
    </div>
    <div class="avatar">
      <img :src="user.avatar" alt="" />
    </div>
  </div>
</template>

<style scoped>
.user {
  display: flex;
  width: 500px;
}

.user div {
  flex: 1;
}

.avatar {
  text-align: right;
}
</style>
