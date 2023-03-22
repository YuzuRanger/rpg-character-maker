<template>
  <div id="app">
      <button v-on:click="toggle='character-viewer'; getCharacters()">View all characters</button>
      <button v-on:click="toggle='character-creator'">Create a character</button>
      <CharacterViewer v-show="toggle==='character-viewer'" :characters="characters"/>
      <CharacterCreator v-show="toggle==='character-creator'" />
  </div>
</template>

<script>
  import CharacterViewer from './components/CharacterViewer.vue'
  import CharacterCreator from './components/CharacterCreator.vue'
  import axios from "axios"
  export default {
      name: 'App',
      components: {
          CharacterViewer,
          CharacterCreator
      },
      data: function () {
          return {
              toggle: "character-creator",
              characters: null
          }
      },
      methods: {
          getCharacters: function () {
              axios
                  .get('http://localhost:3000/characters')
                  .then(response => (this.characters = response.data))
          }
      },
      mounted: function () {
          this.getCharacters();
      }
  }
</script>

<style>
:root {
  --accent1: rgb(232, 72, 40);
  --accent2: rgb(200, 159, 233);
}

body {
  background-image: url("@/assets/background.jpg");
  background-size: auto;
  background-repeat: no-repeat;
}

button {
    -webkit-text-size-adjust: 100%;
    -webkit-tap-highlight-color: transparent;
    -webkit-font-smoothing: antialiased;
    text-shadow: 1px 1px 1px rgba(0,0,0,.004);
    animation-duration: 0.0001s;
    animation-name: mui-btn-inserted;
    font-weight: 500;
    text-transform: uppercase;
    transition: all .2s ease-in-out;
    display: inline-block;
    height: 2.25rem;
    padding: 0 1.625rem;
    margin: .375rem 0;
    border: none;
    border-radius: 2px;
    cursor: pointer;
    touch-action: manipulation;
    background-image: none;
    text-align: center;
    line-height: 2.25rem;
    vertical-align: middle;
    white-space: nowrap;
    user-select: none;
    font-size: .875rem;
    font-family: inherit;
    letter-spacing: .03em;
    position: relative;
    overflow: hidden;
    color: #FFF;
    background-color: var(--accent1);
    margin-left: .5rem;
}

.reset {
    background-color: var(--accent2);
}

.randomize {
    background-color: aquamarine;
}

button:hover {
    -webkit-text-size-adjust: 100%;
    -webkit-tap-highlight-color: transparent;
    -webkit-font-smoothing: antialiased;
    text-shadow: 1px 1px 1px rgba(0,0,0,.004);
    animation-duration: 0.0001s;
    animation-name: mui-btn-inserted;
    font-weight: 500;
    text-transform: uppercase;
    transition: all .2s ease-in-out;
    display: inline-block;
    height: 2.25rem;
    padding: 0 1.625rem;
    margin: .375rem 0;
    border: none;
    border-radius: 2px;
    cursor: pointer;
    touch-action: manipulation;
    background-image: none;
    text-align: center;
    line-height: 2.25rem;
    vertical-align: middle;
    white-space: nowrap;
    user-select: none;
    font-size: .875rem;
    font-family: inherit;
    letter-spacing: .03em;
    position: relative;
    overflow: hidden;
    outline: 0;
    text-decoration: none;
    box-shadow: 0 0 2px rgba(0,0,0,.12),0 2px 2px rgba(0,0,0,.2);
    margin-left: .5rem;
    color: #FFF;
    background-color: var(--accent1);
}

.reset:hover {
    background-color: blueviolet;
}

.randomize:hover {
    background-color: aqua;
}

select {
    -webkit-text-size-adjust: 100%;
    -webkit-tap-highlight-color: transparent;
    font-size: .875rem;
    font-weight: 400;
    line-height: 1.429;
    color: rgba(0,0,0,.87);
    -webkit-font-smoothing: antialiased;
    text-shadow: 1px 1px 1px rgba(0,0,0,.004);
    display: inline-block;
    position: relative;
}

.content-box {
  box-shadow: 0 0 1rem 0 rgba(0, 0, 0, 0.2);
  border-radius: 5px;
  background-color: rgba(255, 255, 255, 0.695);

  backdrop-filter: blur(5px);
}

  #app {
      font-family: Avenir, Helvetica, Arial, sans-serif;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      text-align: center;
      margin: 5vh 5vw;
      padding: 10px;
  }
</style>