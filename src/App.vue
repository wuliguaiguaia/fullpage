<template>
  <div id="app">
     <fullpage></fullpage> 
  </div>
</template>

<script>
import fullpage from '@/components/fullpage.vue'

export default {
  name: 'app',
  components: {
    fullpage
  }
}
</script>

<style>
*{
  box-sizing: border-box;
}
body{
  margin: 0;
}
</style>
