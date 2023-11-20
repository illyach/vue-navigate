<template>
  <div class="app">
    <NavManu />
    <ElementFrame :isMyScrollProp="isMyScroll"/>
    <p :style="{textAlign: 'center',fontSize:'30px', fontWeight:'bold', color: isMyScroll ? 'lightgreen' : 'red'}">{{ isMyScroll }}</p>
  </div>
</template>

<script>
// import MainPage from './components/MainPage.vue'
// import MainTailwind from './components/MainTailwind.vue';
import NavManu from './components/NavManu.vue';
import ElementFrame from './components/ElementFrame.vue'
import { ref, onMounted, onUnmounted, provide } from 'vue';
export default {
  name: 'App',
  components: {
    NavManu,
    ElementFrame
  },
  
  setup(){
      const isMyScroll = ref(false);
      const handleScroll = () => {
        isMyScroll.value = window.scrollY === 90;
        console.log(window.scrollY)
      }

      provide('isMyScrollData', isMyScroll);

      onMounted(() => {
      window.addEventListener("scroll", handleScroll);
    });

    onUnmounted(() => {
      window.removeEventListener("scroll", handleScroll);
    });

    return{
      isMyScroll
    }
  },
  
}

</script>

<style>

</style>

