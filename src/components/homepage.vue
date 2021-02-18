<template>
<div>
     <HelloWorld />
    <img src="../assets/healthify_icon.jpg" width=150px height=130px style="z-index=2;">
    <h1 style="z-index=2;">Healthify.com</h1>
    <h2 style="z-index=2;">Always standing by your side</h2><br>
     <Main1 /> <br><br>
</div>
</template>
<script>
import HelloWorld from './HelloWorld.vue';
import Main1 from './main1';
export default{
     name: 'homepage',
     components : {
        Main1,
         HelloWorld,
     }
}
</script>
<style scoped>
div{
  background-color:black;
  padding:0px;
  margin-top:-5px;
margin-bottom:5px;
}
img{
    float:left;
    margin-left: 10px;
    margin-top: 8px;
}
h1{
    background-color: black;
    color: brown;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-size: 100px;
    margin-top: -4px;
    margin-bottom:0px;
}
h2{
    background-color: black;
    color: brown;
    font-family:Arial, Helvetica, sans-serif;
    font-size: 25px;
    margin-top: 10px;
    margin-bottom:-2px;
}
</style>