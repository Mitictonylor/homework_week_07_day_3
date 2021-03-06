# rick_and_marty

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```


Instruction:
* if u want to see the list of the characters straight away and then the possibility to click on each element and see the details with the search bar:

 from all the html code available comment out line 5 and 6

* if u want a drop list:
 from all the html code available comment out line 6 and 7

### BRIEF
Rick and Morty - Multi Components Homework
Lab Duration: 120 mins

Learning Objectives
Be able to create a Vue app with multiple components and templates
Brief
Your task is to create an app that shows info for all the characters of the TV show Rick and Morty using multiple components. Use the Rick and Morty API to make a request to get the data.

**MVP**
- Display a list of character names.
- Add a click event to the list item which should then render more detail about that character (name, species, status).
- Use reusable components.
**Extensions**
- Instead of rendering a list, populate a dropdown with all of the characters names.
- Add a change event to the select that renders information about the selected character.
**Advanced Extensions**
- Add the characters image and origin name to the character detail component.
- Add a search bar to the page so that when a user enters the characters name the character detail component renders. Try to achieve this without the user having to enter the whole name.
**Planning**
- Draw a diagram of your files, detailing:
- the data, props, components and methods for each component.
- the flow of data throughout the application.
- Expected Components for MVP

- CharacterList
- CharacterDetail
- CharacterSelect
