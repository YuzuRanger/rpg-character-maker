# rpg-character-maker

I started out with [this tutorial](https://www.freecodecamp.org/news/build-a-full-stack-mevn-app/) to build a basic MongoDB, Express, Vue, and Node (MEVN Stack) project that saves character name and class/profession to a database, and pulls from the database to display previously saved characters.

From there I made my own additions and modifications, such as: 
- Set default page to show character creator instead of saved characters
- Added an alert upon submission of new character to database
- Added dropdowns for character Race/Ancestry and Quirks
- Created `module.exports` to populate each dropdown dynamically and to provide a set of random names for use with randomizer
- Added a reset button that clears the form, and a randomizer button that populates each field with random choices

# Screenshots

<picture>
  <img alt="Shows the character creation form prefilled with randomized inputs." src="https://github.com/YuzuRanger/rpg-character-maker/blob/main/client/src/assets/Screenshot%202023-03-21%20223151.png" width="49%">
</picture>

<picture>
  <img alt="Shows a list of generated characters." src="https://github.com/YuzuRanger/rpg-character-maker/blob/main/client/src/assets/Screenshot%202023-03-21%20223114.png" width="49%">
</picture>

# Potential Future Additions

- More names and quirks to choose from
- Input validation, etc.
- More character customization features, such as color pickers for eye and hair color
- Separate button to randomize name only

# Local Setup

tab one - http://localhost:8080/
1. `cd C:\Users\Morgan\Documents\GitHub\rpg-character-maker\client`
2. `npm run serve`

tab two - http://localhost:3000/
1. `cd C:\Users\Morgan\Documents\GitHub\rpg-character-maker\server`
2. `npm run dev`

tab three
1. `cd C:\Users\Morgan\Documents\GitHub\rpg-character-maker`
2. `mongod`

# Other Credits

I got some button CSS from https://www.muicss.com/docs/v1/css-js/buttons
