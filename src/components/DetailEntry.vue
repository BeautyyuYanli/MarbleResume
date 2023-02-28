<script setup>
import DetailSubentry from './DetailSubentry.vue'
defineProps(['title', 'subentries'])
</script>
<template>
  <div class="entry">
    <h2>{{ title }}</h2>
    <ul>
      <li v-for="(subentry, index) in subentries" :key="index">
        <DetailSubentry :subentry="subentry" />
      </li>
    </ul>
  </div>
</template>
<style scoped>
li {
  list-style: none;
}

.entry {
  margin-top: 0.5rem;
}
</style>
