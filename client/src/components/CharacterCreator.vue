<template>
  <div class="character-creator">
      <h1>Character Creator</h1>
      <label for="character-name">Character Name: </label>
      <input type="text" id="character-name" v-model="name" placeholder="Enter a name" /> <br /><br />
      <label for="professions-list">Character Profession: </label>
      <select id="professions-list" v-model="profession">
          <option value="Mage">Mage</option>
          <option value="Thief">Thief</option>
          <option value="Warrior">Warrior</option>
      </select><br /><br />
      <label for="races-list">Character Race: </label>
      <select id="races-list" v-model="race">
          <option value="Elf">Elf</option>
          <option value="Human">Human</option>
          <option value="Dwarf">Dwarf</option>
      </select><br /><br />
      <button v-on:click="postCharacter">Create Character</button>
  </div>
</template>

<script>
  import axios from 'axios';

  export default {
      name: 'CharacterCreator',
      data: function () {
          return {
              name: null,
              profession: null,
              race: null
          }
      },
      methods: {
          postCharacter: function () {
              axios
                  .post('http://localhost:3000/characters', {
                      name: this.name,
                      profession: this.profession,
                      race: this.race
                  });
              this.showAlert();
          },
          showAlert: () => {
            alert('Submitted')
          }
      }
  }
</script>