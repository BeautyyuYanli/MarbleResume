<script setup>
defineProps(['srcs'])
</script>
<template>
  <div>
    <img :src="srcs[0]" alt="Avatar" />
    <span v-if="srcs[1] != null">🔗</span>
    <img v-if="srcs[1] != null" :src="srcs[1]" alt="Avatar" />
  </div>
</template>
<style scoped>
img {
  width: 5rem;
  border-radius: 50%;
  border: 1px solid #888;
}

span {
  margin: 0 0.5rem;
}

div {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  padding: 0;
  margin-bottom: 0.5rem;
}
</style>
