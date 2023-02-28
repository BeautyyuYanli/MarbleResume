<script setup>
import { marked } from 'marked'
defineProps(['name', 'nickname', 'description', 'contacts'])
</script>
<template>
  <div>
    <h1>
      <span class="name">{{ name }} </span>
      <span class="nickname">({{ nickname }})</span>
    </h1>
    <ul>
      <li v-for="(item, key) in contacts" :key="key">
        <img :src="item.icon" :alt="key" />
        <a :href="item.link">
          <span>{{ item.value }}</span>
        </a>
      </li>
    </ul>
    <p id="description" v-html="marked.parse(description)"></p>
  </div>
</template>
<style scoped>
.nickname {
  font-weight: lighter;
  font-style: italic;
  margin-left: 1rem;
}

ul {
  display: flex;
  align-items: baseline;
}

li {
  display: inline-flex;
  font-size: small;
  /* make it center */
  flex-direction: row;
  align-items: center;
  padding: 0 1rem 0.5rem 0;
}

li > img {
  height: 1rem;
  margin-right: 0.25rem;
}

#description {
  text-indent: 1rem;
}
</style>
