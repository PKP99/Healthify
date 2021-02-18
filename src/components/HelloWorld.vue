<template>
  <nav class="navbar sticky-top navbar-expand-lg navbar-dark bg-dark" style="z-index:2">
  <div class="container-fluid">
    <span style="font-size:20px; color:dodgerblue; border-style:solid; border-width: 4px; border-color:dodgerblue; border-radius:15px; ">Get Started</span>
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

      <form class="d-flex">
        <input class="form-control me-2" type="search" placeholder="Search Content" aria-label="Search">
        <button class="btn btn-outline-success" type="submit">Search</button>
        
        <b-dropdown right text="LANGUAGES" style="color:black; margin-left:10px; margin-right:10px">
      <b-dropdown-item>English</b-dropdown-item><hr>
      <b-dropdown-item>Hindi</b-dropdown-item>
    </b-dropdown>
    <b-dropdown right text="USER" style="color:black; margin-left:10px; margin-right:10px">
      <b-dropdown-item>LOG IN</b-dropdown-item><hr>
      <b-dropdown-item>LOG OUT</b-dropdown-item><hr>
      <b-dropdown-item>GUEST</b-dropdown-item>
    </b-dropdown>
      </form>
    </div>
  </div>
</nav>
</template>

<script>
export default {
    name: 'HelloWorld',
}
</script>