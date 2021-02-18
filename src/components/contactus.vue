<template>
    <div>
        <nav class="navbar fixed-bottom navbar-expand-lg navbar-dark bg-dark" style="z-index:2">
  <div class="container-fluid">
    
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item" style="margin-left:20px">
          <a class="nav-link" aria-current="page" href="#" style="font-size:20px;">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#" style="font-size:20px;">Events</a>
        </li>
         <li class="nav-item">
          <a class="nav-link" aria-current="page" href="#" style="font-size:20px;">Train</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#" style="font-size:20px;">Learn</a>
        </li>
      </ul>
      <span style="margibn-right:30px;color:red; font-size:20px; border-right: 10px solid white ; border-left: 10px solid white; padding:5px 20px "><b>&#169; PKP_2021 &#174;</b></span>

      <form class="d-flex" style="margin-bottom: -100px;">
         
           <a href="https://www.facebook.com/paraskumar.patel.77/" target="_blank"> <button class="btn3" style=" margin-left:100px;">Latest Events</button> </a><br><br>
       <button class="btn3">Calorie Counter</button> <br><br>
      <button class="btn3">User Review</button> <br><br>
       <button class="btn3">About Us</button> <br><br>
       <button class="btn3" style="margin-bottom:100px">Contact Us</button>

      </form>
    </div>
  </div>
</nav>
    </div>
</template>

<script>

export default {
    name: 'contactus',
}
</script>

<style scoped>
.btn3 {
  border: 2px solid black;
  background-color: white;
  color: black;
  font-size: 17px;
  font-weight: bold;
  cursor: pointer;
  border-color:green;
  color: green;
  width: 150px;
  height:30px;
  border-radius: 5px;
  margin-left:10px;
}
.btn3:hover {
   background: green;
  color: white;
}

</style>