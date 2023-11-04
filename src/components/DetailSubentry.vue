<script setup>
import { marked } from 'marked'
defineProps(['subentry'])
</script>
<template>
  <div id="subentry">
    <div id="header">
      <h3 v-html="marked.parse(subentry.title)"></h3>
      <div id="subheader">
        <div>
          <h4 v-if="subentry.subtitle != null" v-html="marked.parse(subentry.subtitle)"></h4>
        </div>
        <span>{{ subentry.date }}</span>
      </div>
    </div>
    <p
      id="description"
      v-if="subentry.description != null"
      v-html="marked.parse(subentry.description)"
    ></p>
  </div>
</template>
<style scoped>
#subentry {
  margin-bottom: 0.5rem;
}

#header {
  border-left: 3px solid #888;
  padding-left: 1rem;
  margin-bottom: 0.25rem;
}

#subheader {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h4 {
  font-weight: lighter;
  font-style: italic;
}

#description {
  text-indent: 1rem;
}
</style>
