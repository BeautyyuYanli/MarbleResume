<script setup>
defineProps(['tags', 'title'])
</script>
<template>
  <div class="tags">
    <h4>{{ title }}</h4>
    <ul>
      <li v-for="(tag, index) in tags" :key="index">
        <span>{{ tag }}</span>
      </li>
    </ul>
  </div>
</template>
<style scoped>
ul {
  display: flex;
  flex-wrap: wrap;
}

ul > li {
  list-style: none;
  margin: 0.2rem 0.2rem;
  padding: 0rem 0.5rem;
  border: 1px solid #888;
  border-radius: 999px;
  font-size: small;
}

.tags {
  padding: 0.5rem;
  border-bottom: 1px solid #888;
}
</style>
