<template>
 <header>

  <div class="wrapper">
   <div class="container">
    <nav class="nav__global">
     <RouterLink to="/">Home</RouterLink>
     <RouterLink to="/about">About</RouterLink>
    </nav>
   </div>
  </div>
 </header>

 <RouterView />
</template>

<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<style>
.nav__global {
 display: flex;
 gap: 1em;
 padding: 2vh 0;
}

.container {
 width: 80%;
 margin: 0 auto;
}

* {
 padding: 0;
 margin: 0;
 box-sizing: border-box;
}

a {
 text-decoration: none;
 font-size: 2vh;
 color: #090909;
 font-weight: 500;
}
</style>
