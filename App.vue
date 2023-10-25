<template>
import Vue from'vue';
  <h1 class="text-3xl font-bold underline text-emerald-600">
   STAR WARS
 
  <button @click="showForm = true" :class="{ choosen: showForm }">
    New character
  </button>
  <button @click="showForm = false" :class="{ choosen: !showForm }">
Character  </button> -->
  <!-- <Form v-if="showForm" @sendCharactertoApp="addCharacter" /> -->
  <input type="number" name="charNum" v-model="charNum"/>
  <button @click="getChar">get character</button>
  
  <h2 v-if="character">{{ character.name }}</h2>
 
</template>

<script>
  export default {name: "App",
  components:characersList, Form}
    data(){
      return{ showForm: true,
      character: "",
      planet: "",
      charNum: "",}
    }
  




    return {
      
      showForm: true,
      character: "",
      planet: "",
      charNum: "",
    };
  
  methods: {
    addCharacter(characterfromForm) {
      this.characters.push(characterfromForm);
      console.log(this.characters);
      return this.characters;
    },
    getChar() {
      fetch(`https://swapi.dev/api/people/${this.charNum}/`)
        .then((response) => response.json())
        .then((data) => {
          this.charNum = ""
          return this.character = data})
        .catch((error) => console.log(error));
    },
    async getPlanet(){
      const response = await fetch(`https://swapi.dev/api/planets/${Math.floor(Math.random() * 22)+1}/`)
      const data = await response.json()
      return this.planet = data
    };
  }
  computed: {
    StarWarsSentence() {
      return ` Character: ${this.characters[this.characterslength - 1].name}`;
    },

  },

</script>

<style>
/* CSS */
.choosen {
  background-color: rgb(29, 217, 192);
  color: rgb(42, 42, 42);
  font-weight: bold;
}

#cover-image {
  display: block;
  margin-bottom: 5%;

}

</style>




    