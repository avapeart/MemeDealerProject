<template>
  <div class="home">
   <input id='inputBox' type="text" v-model="search" placeholder="Search memes...">
    <!-- <img id="certified" src="../assets/certified.png" > -->
    <!-- <h2 id="maintext">Seach thousands of memes with just one click!<br> OR <br> Scroll down to see all our memes!</h2>
     -->
    <div id="main">
    <div class="grid-container">
    <div class="grid-item" v-for="(meme, index) in searchFilter" v-bind:key="index">
        <div>
            <img :src="meme.media" />
                <br>
            <h2> Title: {{meme.title}}</h2>
                <br><br>
        </div>
    </div>
    </div>
</div>
    
  
  </div>
</template>

<script>
// import SearchPage from '@/components/SearchPage'
import data from '@/components/db.js';

export default {
  name: 'home',
  components: {
   
  },
   data(){
        return{
        memes: data._default,
        search: ''
        }
    },
   computed: {
    searchFilter: function(){
        return Object.values(this.memes).filter((val)=>{
            return val.title.includes(this.search);
        })
    }
}
}
   
</script>

<style lang="scss">

.home{
  padding-top: 20px;
  background: no-repeat;
  background-size: 100%;
    background-image: url("../assets/bg2.png");
}
h1{ 
  
  margin-top: 0%;
  padding-top: 0px;
   font-size: 300%;
    font-weight: bold;
    color: #2c3e50;
}
footer{
  padding: 30px;
  bottom: 0;
  width: 100%;
  height: 2.5rem; 
  color:white;
  background-color: #212121;
  position:relative; 
}
#logo{
  padding-left: 60%;
  display: inline-block;
}
#inputBox{
    align-self: center;
    border-radius: 10px;
    border-width: 2px;
    border-color: black;
    text-align: center;
    width: 650px;
    font-size: 17px;
    height: 40px;
    margin-left: 30%;
    margin-top: 65px;
    margin-bottom: 140px;
    // margin-right:35%; 
    // float: right;

}
#maintext{
  text-align: center;
  position:relative;
  padding-left: 45%;
  margin-top: 0%;
  
  
}
#certified{
  margin-top: 0px;
  display: inline-block;
  margin-left: 38%;
}

//all for the search page
#main{
    margin: 0;
    background-color:white; 
}


h2{
   padding-top: 0px;
   font-size: 155%; 
    font-weight: bold;
    color: #2c3e50;
}

img {
    height: 320px;
    width: 400px;
}

.grid-container {
  display: grid;
  grid-column-gap: 0;
  grid-template-columns: auto auto auto;
  padding: 10px;
  overflow: hidden;
}

.grid-item {
  padding: 20px;
  text-align: center;
  overflow: hidden;
}

</style>


