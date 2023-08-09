<template>
  <header class="header ">
    <div class="wrapper">
      <div class="header-main">
        <div class="menu-link d-flex justify-content-space-between">
          <ul class="menu-list">
            <li class="menu-item" v-for="(item, index) in menu" :key="index">
              <a :href="item.href" :class="'menu-link '+ item.class" v-bind="item.class">{{ item.title }}</a>
            </li>
          </ul>
          <div class="menu-user">
            <li class="menu-item">
              <a href="#work" class="menu-link">Service</a>
            </li>
            <li class="menu-item">
              <a href="#experience" class="menu-link">Blog</a>
            </li>
            <li class="menu-item">
              <a href="#contact" class="menu-link">Contact</a>
            </li>
          </div>
        </div>
      </div>
    </div>
  </header>
  <div class="wrapper">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      menu: [
        { title: "John Doe", href: "john@example.com", class: '' },
        { title: "Jane Smith", href: "jane@example.com" },
        { title: "Michael Johnson", href: "michael@example.com" },
        // Thêm dữ liệu giả khác ở đây
      ],
    };
  },
}
</script>

<style lang="sass">
@import ./assets/sass/template

.wrapper
  margin: 0 auto
  max-width: $max-container

$align-items: ('start': flex-start, 'center': center, 'end': flex-end)
@each $name, $position in $align-items
  .align-items-#{$name}
    align-items: $position

$display: flex, inline-flex, block, inline-block
@each $var in $display
  .d-#{$var}
    display: $var

$justify-content: center, start, end, flex-start, flex-end, space-between
@each $var in $justify-content
  .justify-content-#{$var}
    justify-content: $var


// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
//   margin-top: 60px;
// }
</style>
