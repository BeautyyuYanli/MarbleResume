<script setup>
defineProps(['title', 'cards'])
</script>
<template>
  <div class="cards">
    <h4>{{ title }}</h4>
    <ul>
      <li v-for="(card, index) in cards" :key="index">
        <div v-if="card.date != null">
          <p class="title">{{ card.title }}</p>
          <div>
            <p class="date">{{ card.date }}</p>
            <p class="subtitle">{{ card.subtitle }}</p>
          </div>
        </div>
        <div v-if="card.date == null">
          <div>
            <p class="title">{{ card.title }}</p>
            <p class="subtitle">{{ card.subtitle }}</p>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>
<style scoped>
li {
  padding: 0.2rem 0;
}

li > div {
  display: flex;
  flex-direction: column;
}

li > div > div {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.subtitle {
  font-weight: bold;
  flex-shrink: 0;
  margin-left: 1rem;
}

p {
  font-size: small;
}

.date {
  font-style: italic;
  font-size: x-small;
}

.cards {
  padding: 0.5rem;
  border-bottom: 1px solid #888;
}
</style>
