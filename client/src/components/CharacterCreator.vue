<template>
  <div class="character-creator">
      <h1>Character Creator</h1>
      <label for="character-name">Character Name: </label>
      <input type="text" id="character-name" v-model="name" placeholder="Enter a name" /> <br /><br />

      <label for="races-list">Character Race: </label>
      <select id="races-list" v-model="race">
          <option value="Elf">Elf</option>
          <option value="Human">Human</option>
          <option value="Dwarf">Dwarf</option>
      </select><br /><br />
            
      <label for="professions-list">Character Profession: </label>
      <select id="professions-list" v-model="profession">
          <option value="Mage">Mage</option>
          <option value="Thief">Thief</option>
          <option value="Warrior">Warrior</option>
      </select><br /><br />

      <label for="backgrounds-list">Character Background: </label>
      <select id="backgrounds-list" v-model="background">
          <option value="Bandit">Bandit</option>
          <option value="Acolyte">Acolyte</option>
          <option value="Barkeep">Barkeep</option>
      </select><br /><br />

      <label for="quirks-list">Character Quirk: </label>
      <select id="quirks-list" v-model="quirk">
          <option value="Afraid of a Magical Element">Afraid of a Magical Element</option>
          <option value="Bound to an Oath">Bound to an Oath</option>
          <option value="Overly Flirtatious">Overly Flirtatious</option>
      </select><br /><br />

      <button v-on:click="postCharacter">Save Character</button>
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
              race: null,
              background: null,
              quirk: null
          }
      },
      methods: {
          postCharacter: function () {
              axios
                  .post('http://localhost:3000/characters', {
                      name: this.name,
                      profession: this.profession,
                      race: this.race,
                      background: this.background,
                      quirk: this.quirk
                  });
              this.showAlert();
          },
          showAlert: () => {
            alert('Submitted')
          }
      }
  }
</script>