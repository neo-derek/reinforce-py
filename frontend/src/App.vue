<template>
  <div id="app">
    <my-menu v-model="menuSelectedIndex" v-on:selectedIndexChange="onMenuSelectedIndexChange"></my-menu>

    <transition name="fade" mode="out-in">
      <router-view/>
    </transition>
  </div>
</template>

<script>
import MyMenu from '@/components/MyMenu.vue';

export default {
  name: 'App',
  components: {
    MyMenu
  },
  data: function () {
    return {
      menuSelectedIndex: 0
    }
  },
  created () {
  },
  methods: {
    onMenuSelectedIndexChange(index) {
      this.menuSelectedIndex = index;
    }
  }
};
</script>

<style>
@font-face {
  font-family: "monaco";
  src: url("./assets/fonts/monaco.ttf");
}

@font-face {
  font-family: "roboto";
  src: url("./assets/fonts/roboto.ttf");
}

h1 {
  font-family: "roboto";
  font-size: 2.0rem;
  text-align: center;
  text-shadow: 0 3px 2px #aaa;
  color: #6c7a89;
}

p {
  font-family: "roboto";
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  width: 100vw;
  height: 100vh;

  display: flex;
  flex-direction: column;
  align-items: stretch;
}

.fade-enter-active,
.fade-leave-active {
  transition-duration: 0.06s;
  transition-property: opacity;
  transition-timing-function: ease;
}

.fade-enter,
.fade-leave-active {
  opacity: 0
}
</style>
