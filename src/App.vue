<template lang="html" >
  <div class="parallax">
<header-item></header-item>

<!-- <select-character :characters="characters"></select-character> -->
<!-- <filtered :characters="characters"></filtered> -->
<r-m-list :characters="characters"></r-m-list>
<character-detail v-if="selectedCharacter" :character="selectedCharacter"></character-detail>
</div>
</template>

<script>
import Header from "./components/Header.vue"
import{eventBus} from './main.js'
import RMList from "./components/RMList.vue"
// import Filtered from './components/Filtered.vue'
import SelectCharacter from './components/SelectCharacter.vue'
import CharacterDetail from './components/CharacterDetail.vue'

export default {
  name: "app",
  data() {
    return {
      characters: [],
      selectedCharacter :null
    }},

components:{
            "header-item": Header,
            "r-m-list": RMList,
            'character-detail': CharacterDetail,
            'select-character': SelectCharacter,
            // 'filtered': Filtered

},

methods:{

},
mounted(){
  fetch('https://rickandmortyapi.com/api/character/')
  .then(result => result.json()).then(characters => this.characters = characters.results)

  eventBus.$on('char-selected', (character) =>{
    this.selectedCharacter = character})

    eventBus.$on('input',(selectedChar) => {this.selectedCharacter = selectedChar})
}
}
</script>

<style lang="css" scoped>
/* @font-face {
  font-family: get_schwiftyimport;
  src:url("./assets/get_schwifty.ttf");

} */

.parallax {
  /* The image used */
  background-image:url(https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/93b70d31-3648-498f-8096-0ede60bc5e11/d9kcpul-e1f6f4ff-373c-421e-9133-7825b6c80d8a.jpg/v1/fill/w_1192,h_670,q_70,strp/rick_and_morty__crombuliar_ball_by_wakerdre_d9kcpul-pre.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7ImhlaWdodCI6Ijw9NzIwIiwicGF0aCI6IlwvZlwvOTNiNzBkMzEtMzY0OC00OThmLTgwOTYtMGVkZTYwYmM1ZTExXC9kOWtjcHVsLWUxZjZmNGZmLTM3M2MtNDIxZS05MTMzLTc4MjViNmM4MGQ4YS5qcGciLCJ3aWR0aCI6Ijw9MTI4MCJ9XV0sImF1ZCI6WyJ1cm46c2VydmljZTppbWFnZS5vcGVyYXRpb25zIl19.KkTu5ELGS9YYNfvuz6jj62WpZ3DnvgiZV70P_2R2uTo);

  /* Full height */
  height: 100%;

  /* Create the parallax scrolling effect */
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

h1{
font-size: 50px;
color: yellow;
background-color: blue;
text-align: center;

}
h3{
  font-size: 20px;
  margin: 0;
  padding: 0
}
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family:  get_schwiftyimport;
  font-size: 30px;
  background-color: rgba(255, 255, 255, .8)


}
li{
  position: relative;
    padding-left: 11px;
  margin: 0 0 3px 0;
  line-height: 10.4;

}
ul {
    font-size: 13px;
    list-style: none;
    margin: 0 0 0 -0.8125em;
    padding-left: 0;
}

.btn{
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover{
  background: #666
}

form{
  display: flex
}
input[type="text"]{
  flex: 40;
  padding: 5px;
  background-color: grey
}
input[type='submit']{
  flex: 8;

}
select{
  flex:10
}
</style>
