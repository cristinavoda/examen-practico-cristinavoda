<template>
  <ul>
    <li v-for="(characters, i) in charactersFromApp" :key="i">
      <h4>{{ character.name }}</h4>
      <img :alt="character.name" :src="character.image" width="400"/>
      <p>{{ character.about }}</p>
  </ul>
</template>

<script>
export default {
  name: "CharacersList",
  props: ["characterFromApp"],
  data() {
    return {};
  },
};
</script>

<style>
ul {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
    list-style: none;
}
</style>
