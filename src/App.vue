<template>
  <header class="header">
    <div class="header_main">
      <div class="wrapper">
        <div class="menu-link d-flex justify-content-space-between ml-1 mr-1">
          <ul class="menu-inline menu-list">
            <li class="menu-item" v-for="(item, index) in menu" :key="index">
              <a :href="item.href" :class="menu-link">{{ item.title }}</a>
            </li>
          </ul>
          <div class="menu-inline menu-user">
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
        { title: "総合トップ", href: "/",},
        { title: "ショッピング", href: "/" },
        { title: "中古パーツ", href: "/" },
        { title: "バイク選び", href: "/" },
        { title: "ショップNAVI", href: "/" },
        { title: "メディア総合", href: "/" },
        { title: "サービス", href: "/" },
        { title: "コミュニティ", href: "/" },
        { title: "イベントNAVI", href: "/" },
        { title: "レース", href: "/" },
        { title: "EWC", href: "/" },
        { title: "ご利用案内", href: "/" },
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

$position: top, right, bottom, left

@for $var from 0 through 5
  .m-#{$var}
    margin: 10px*$var
  .p-#{$var}
    padding: 10px*$var
    
  @each $p in $position
    .m#{str-slice($p, 0, 1)}-#{$var}
      margin-#{$p}: 10px*$var
    .p#{str-slice($p, 0, 1)}-#{$var}
      padding-#{$p}: 10px*$var

header.header
  $spacing: 10px
  $black-blue: #2a313c
  $red: #e61e25
  .header_main
    background: $black-blue
    border-bottom: 3px solid $red
    .menu-inline
      display: block
      >li
        display: inline-block
        transition: .325s
        &:hover
          background: $red
        &.current
          background: $red
    .menu-item
      >a 
        color: $white
        line-height: 1.5
        display: block
        padding: $spacing*.8

// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
//   margin-top: 60px;
// }
</style>
