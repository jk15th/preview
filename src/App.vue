<!-- src/layouts/DefaultLayout.vue -->
<template>
  <HeaderTag/>
  <div>
    <router-view />
    <slot></slot>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';
import HeaderTag from './components/header/header-tag.vue';

export default {
  name: 'App',
  components: {
    HeaderTag,
  },
};
</script>