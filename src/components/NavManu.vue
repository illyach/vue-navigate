<template>

<div>
  <button @click="openMenu">Open</button>
  <Transition name="slide">
  <div class="menu" v-if="menuCondition">
    <ul>
      <li>Get info</li>
      <li>Company</li>
      <li>Abous us</li>
      <li>Contacts</li>
    </ul>

    <button @click="openMenu">Close Menu</button>
  </div>
</Transition>
</div>
   
</template>

<script setup>
import { ref } from 'vue';
const menuCondition = ref(false);
const openMenu = () => {
  menuCondition.value = !menuCondition.value
}
</script>

<style>
.menu{
  position: absolute;
  top:-15px;
  background-color: rgb(30, 25, 25);
  color:white;
  font-size: larger;
  height: 100%;
  width: 300px;
  transform: translateX(-3%);
  transition: all .3s ease-out;
}
.menu ul{
  list-style: none;
}

.button{
  padding: 10px;
  margin: 10px;
}

.menu li{
  padding: 20px;
}
.slide-enter-active,
.slide-leave-active {
  transition: right 0.3s ease-out; 
}
.slide-enter-active {
 
  transform: translateX(-100%);
 
}

.slide-leave-to .slide-leave-active{
  transform: translateX(-10%);
}





</style>


<!-- .menu {
  position: fixed;
  top: -15px;
  width: 150px;
  height: 100%;
  background-color: rgb(248, 248, 248);
  z-index: 100;
  transition: right 0.3s ease; /* Добавлен переход */
}

.menu li {
  list-style-type: none;
  padding: 10px;
}
.menu button{
  width: 70px;
  margin:10px;
} -->