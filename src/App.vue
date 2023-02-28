<script setup>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
import AvatarsComponent from './components/AvatarsComponent.vue'
import BasicProfile from './components/BasicProfile.vue'
import DetailEntry from './components/DetailEntry.vue'
import TagsComonent from './components/TagsComonent.vue'
import CardsComponent from './components/CardsComponent.vue'
import config from '../config.json'
import { marked } from 'marked'
console.log(config)
</script>

<template>
  <header>
    <AvatarsComponent :srcs="config.avatars" />
    <TagsComonent
      :tags="config.programming_languages"
      :title="config.constant.programming_languages"
    />
    <TagsComonent :tags="config.knowledge" :title="config.constant.knowledge" />
    <CardsComponent :cards="config.education" :title="config.constant.education" />
    <CardsComponent :cards="config.honor" :title="config.constant.honor" />
    <CardsComponent :cards="config.languages" :title="config.constant.languages" />
    <CardsComponent :cards="config.community" :title="config.constant.community" />
    <p id="credit" v-html="marked.parse(config.credit)"></p>
  </header>

  <main>
    <BasicProfile
      :name="config.name"
      :nickname="config.nickname"
      :description="config.description"
      :contacts="config.contacts"
    />

    <ul>
      <li v-for="(entry, index) in config.detail_entries" :key="index">
        <DetailEntry :title="entry.title" :subentries="entry.subentries" />
      </li>
    </ul>
  </main>
</template>

<style scoped>
header {
  width: 30%;
  display: flex;
  flex-direction: column;
  padding-right: 1rem;
  /* place-items: center; */
}

main {
  width: 70%;
  display: flex;
  flex-direction: column;
}

main > li {
  list-style: none;
}

#credit {
  font-size: x-small;
  margin-top: 1rem;
  font-style: italic;
}
</style>
