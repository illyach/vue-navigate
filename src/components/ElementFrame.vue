<template>
    <div class="element">
    <button @click="toggleClick">
            Open2
      </button>
      <transition name="fade">
        <p v-if="show">hello from New York</p>
      </transition>
    </div>

    <div class="element">
        <transition name="image">
            <img v-if="showImage" src="../assets/1.jpg">
        </transition>
    </div>
      


    <div>
        scroll position {{  isMyScrollData }}
    </div>
</template>

<script setup>
import { ref } from 'vue';
import { inject } from 'vue';



const isMyScrollData = inject('isMyScrollData', { type: Boolean, default: false });

console.log(isMyScrollData.value);


//button effect
const show = ref(false);
const showImage = ref(true);

const toggleClick = () => {
    show.value = !show.value
    console.log(show.value)
}




</script>

<style>
.element{
    display: flex;
    justify-content: center;
}

.element img{
    position: relative;
    top:800px;
    width: 300px;
    height: 300px;
   
}




.fade-enter-active,
.fade-leave-active {
  transition: 0.25s;
}

.fade-enter-from {
  opacity: 0;
  margin-right: 300px;
}

.fade-leave-to {
  opacity: 0;
  margin-right: 10px;
}
  
</style>