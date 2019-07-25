<template>
  <div id="app">
      <p id="topBar">Email - meme_dealer@gmial.com &emsp; Phone - (876) 576-4896    </p>
    <h1 id="firsth1"><img id="memelogo" alt="Memes logo" src="./assets/memelogo.png">MEME DEALER </h1>
    <NavBar id="navBar"></NavBar>
    <router-view/>
     <footer>@Copyright 2019-2020 Meme Dealer. All rights reserved.</footer>
  </div>
</template>




<script>
import NavBar from './components/NavBar';

export default {


   data(){
      return{
          
      }
    },

  name: 'App',

  components: {
    NavBar
  },

  // mounted(){
  //   console.log("Mounted");
  // }
 
}

</script>



<style lang="scss">

#app {
  // background-image: url("./assets/bg2.png");
  background-size: cover;
  // background-repeat: no-repeat;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  position: absolute;
  top: 0;
  left: 0;
  height: 100vh;
  background-color: #212121;
  width: 100%;
  overflow:auto;
}
#firsth1{ 
  padding-left: 30px;
  padding-top: 20px;
   font-size: 250%;
    font-weight: bold;
    color: white;
    display: inline-block;
    background-color: #212121;
}
footer{
  padding: 30px;
  bottom: 0;
  width: 100%;
  height: 2.5rem; 
  text-align:center;
  position: relative; 
  background-color:aliceblue;
}
#memelogo{
  padding-top:5px;
  margin-top:15px;
  width:55px;
  height:32px;
}

#topBar{
  background-color: black;
  width: 100%;
  height: 35px;
  padding-top:5px;
  padding-left: 30px;
  margin:0;
  color: grey;
}

#navBar{
  display: inline-block;
  padding-left: 60%;
    background-color: #212121;
  a {
    
    font-weight: bold;
    font-size: 22px;
    color: white;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

</style>
