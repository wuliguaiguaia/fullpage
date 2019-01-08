<template>
  <div class="pages" @wheel="wheelEvent">
    <transition-group :name="name" tag="div">
      <div
        class="page"
        v-for="(page,index) in pages"
        v-show="index === curIndex"
        :key="page"
        :style="{'background-color':bgColor[index]}"
      >{{index+1}}</div>
    </transition-group>
    <button @click="wheelEvent">{{name}}</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      bgColor: ["red", "orange", "yellow", "green"],
      pages: 4,
      curIndex: 0,
      canmove: true,
      name:"down"
    };
  },
  methods: {
    wheelEvent(e) {
      console.log(e,e.deltaMode)
      if(this.name === 'down'){
        if(this.curIndex === this.pages -1) {
          return;
        }
        this.curIndex ++;
      }
    }
  }
};
</script>

<style scoped>
button{
  position: fixed;
  top: 0%;
  right: 0;
  z-index: 9999;
  padding: 10px 20px;
}
.down-enter {
  transform: translateY(100%);
}
.down-enter-active {
  transform: translateY(0);
  transition: transform 2s;
}
.down-leave {
  transform: translateY(0);
}
.down-leave-active {
  transform: translateY(-100%);
  transition: transform 2s;
}

.pages {
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

.page {
  width: 100vw;
  height: 100vh;
}
</style>
