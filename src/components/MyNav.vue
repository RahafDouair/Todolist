<template lang="">
    <!-- <div class="myNav">
       <ul>
        <li v-for="route in router.options.routes" :key="route.name">
        <router-link :to="{name: route.name}">{{route.name}}</router-link>
        </li>
       

       </ul> 
    </div> -->
<div class="cont">
    <nav class="navbar navbar-expand-lg  px-2">
  <a class="navbar-brand" href="#">TodoList</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li  v-for="route in router.options.routes" :key="route.name" class="nav-item nav-link active">
        <router-link class="route" :to="{name: route.name}">{{route.name}}</router-link>
      </li>
     
     
     
    </ul>
   
  </div>
</nav>
</div>
</template>
<script setup>
import {useRouter} from 'vue-router';
const router =useRouter();
console.log(router);
</script>
<style >
   /* route-link{
    text-decoration: none !important;
    color: #000 !important;
    text-transform: capitalize !important;
}  */
.route{
    color: #fff !important;
    text-decoration: none !important;
    /* background-color:#252435; */
    text-transform: capitalize !important;

}
.navbar{
    background-color:#57c389;
}
</style>