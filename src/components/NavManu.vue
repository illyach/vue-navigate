<template>
     <div id="app">
        <button @click="openMenu">≡ open menu</button>
        <ul class="menu" v-if="isOpen">
            <li><a href="#">Home</a></li>
            <li><a href="#">About Us</a></li>
            <li><a href="#">Services</a></li>
            <li><a href="#">Contact</a></li>
            <button @click="closeMenu">X</button>
        </ul>
      </div>
</template>

<script>
export default {
  data () {
    return {
      isOpen: false
    }
  },
  methods: {
    openMenu () {
      this.isOpen = true
    },
    closeMenu () {
      this.isOpen = false
    }
  }
}
</script>

<style>


.menu {
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
  }
  

.slide-enter-active, .slide-leave-active {
    transition: right 0.3s ease;
  }

.slide-enter, .slide-leave-to {
    right: 0;
  }
</style>