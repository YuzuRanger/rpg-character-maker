<template>
  <div class="character-creator">
      <h1>Character Creator</h1>
      <label for="character-name">Character Name: </label>
      <input type="text" id="character-name" v-model="name" placeholder="Enter a name" /> <br /><br />

      <label for="race">Character Race: </label>
      <select id="races-list" v-model="race">
          <option :value="race.name" v-for="(race) in raceSelect" :key="race.code">{{race.name}}</option>
      </select><br /><br />
            
      <label for="profession">Character Class: </label>
      <select id="professions-list" v-model="profession">
        <option :value="profession.name" v-for="(profession) in professionSelect" :key="profession.code">{{profession.name}}</option>
      </select><br /><br />

      <label for="background">Character Background: </label>
      <select id="backgrounds-list" v-model="background">
        <option :value="background.name" v-for="(background) in backgroundSelect" :key="background.code">{{background.name}}</option>
      </select><br /><br />

      <label for="quirk">Character Quirk: </label>
      <select id="quirks-list" v-model="quirk">
        <option :value="quirk.name" v-for="(quirk) in quirkSelect" :key="quirk.code">{{quirk.name}}</option>
      </select><br /><br />

      <!--<label for="country">Your Country</label>
      <select id="countries-list" v-model="country">
          <option :value="country.name" v-for="(country) in countryList" :key="country.code">{{country.name}}</option>
        </select><br /><br /> -->

      <button v-on:click="postCharacter">Save Character</button>
      <button @click="resetInput">Reset</button>
  </div>
</template>

<script>
  import axios from 'axios';

  // let countries = require('../data/countries.js');
  let raceList = require('../assets/races.js');
  let professionList = require('../assets/professions.js');
  let backgroundList = require('../assets/backgrounds.js');
  let quirkList = require('../assets/quirks.js');

  export default {
      name: 'CharacterCreator',
      data: function () {
          return {
              name: null,
              profession: null,
              race: null,
              background: null,
              quirk: null,
              raceSelect: raceList,
              professionSelect: professionList,
              backgroundSelect: backgroundList,
              quirkSelect: quirkList
              // countryList: countries,
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
          },
          resetInput () {
            this.name = "";
            this.profession = "";
            this.race = "";
            this.background = "";
            this.quirk = "";
          }
      }
  }
</script>