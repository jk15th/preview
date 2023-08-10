<template>
    <header class="header">
        <div class="header_main">
            <div class="wrapper">
                <div class="menu-link d-flex justify-content-space-between align-items-center ml-1 mr-1">
                    <ul class="menu-inline menu-list">
                        <li class="menu-item" v-for="(item, index) in menu" :key="index">
                            <a :href="item.href" :class="menu - link">{{ item.title }}</a>
                        </li>
                    </ul>
                    <div class="menu-inline menu-user before-signin ">
                        <li class="sign-in text-white d-flex justify-content-center align-items-center">
                            <figure class="round-circle ">
                                <img src="https://cdn.bhdw.net/im/the-god-of-high-school-jin-mori-god-form-wallpaper-71519_w635.webp"
                                    alt="">
                            </figure>
                            <span>ログイン / 新規会員登録</span>
                            <ul class="hidden_bar-user pt-1 pb-1">
                                <li class="d-block pl-1 pr-1">
                                    <a class="btn btn-block btn-red btn-border-4"
                                        href="https://www.webike.net/shopping/my-webike/index.html">Myショッピング</a>
                                </li>
                                <li class="d-block pl-1 pr-1">
                                    <p
                                        class="btn btn-border-4 pl-1 pr-1 height-sm m-0-auto bg-gray text-black-blue width-fit-content">
                                        アカウントサービス</p>
                                </li>
                                <li class="d-block pl-1 pr-1">
                                    <ul class="account_list_hidden">
                                        <li class="d-block point_detail_block">
                                            <div
                                                class="text-black-blue d-flex justify-content-space-between align-items-center">
                                                <p class="point_detail_title">総保有ポイント</p>
                                                <p class="point_detail_text d-flex" id="total_point">
                                                    <img class="point_icon"
                                                        src="https://img.webike.net/img/w_spng_sp_point_icon.png"
                                                        alt="w_spng_sp_point_icon.png">
                                                    <span>0pt</span>
                                                </p>
                                            </div>
                                            <div
                                                class="text-black-blue d-flex justify-content-space-between align-items-center">
                                                <p class="point_detail_title">まもなく失効</p>
                                                <p class="point_detail_text" id="point_lost_text">0pt</p>
                                            </div>
                                        </li>
                                        <li class="d-block devide-bottom-gray pb-1">

                                            <a class="point_check btn btn-border-4 height-sm m-0-auto btn-red-outline text-black-blue width-fit-content"
                                                href="https://www.webike.net/wbs/point-top.html">ポイントの確認</a>
                                        </li>
                                        <li class="d-block">
                                            <p class="btn btn-border-4 height-sm m-0-auto bg-gray text-black-blue ">中古パーツ
                                            </p>
                                        </li>
                                        <li class="account_nav_list d-block">
                                            <a class="account_nav_list_link"
                                                href="https://www.webike.net/garage-info/precautions_use">ご利用の注意点</a>
                                        </li>
                                        <li class="account_nav_list d-block">
                                            <a class="account_nav_list_link"
                                                href="https://www.webike.net/garage-info/trouble_buyyer">困ったとき</a>
                                        </li>
                                    </ul>
                                </li>
                                <li class="d-block devide-top-black-blue pt-1">
                                </li>
                            </ul>
                        </li>
                    </div>
                </div>
            </div>
        </div>
    </header>
    <div class="wrapper">
        <!-- <img alt="Vue logo" src="./assets/logo.png">
      <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    </div>
</template>
<script>

export default {
    name: 'HeaderMain',
    data() {
        return {
            menu: [
                { title: "総合トップ", href: "/", },
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
@import ../../assets/sass/template

header.header
  .header_main
    background: $black-blue
    border-bottom: 3px solid $red
    .menu-inline
      display: block
      .menu-item
        display: inline-block
        transition: .325s
        &:hover
          background: $red
        &.current
          background: $red
    .menu-user
      position: relative
      .sign-in
        height: 34px
        padding: 0
      .round-circle
        width: 30px
        height: 30px
        border: 1px solid #8e8e8e
        border-radius: 100%
        margin-right: $spacing*.5
        overflow: hidden
        background: $white
        >img
          width: 100%
          height: 100%
          object-fit: cover
      .hidden_bar-user
        position: absolute
        display: none
        width: calc((1280px / 5) - 10px - (2px*2))
        background: $white
        top: 100%
        right: 0
        border-top: 3px solid $red
        transition: .325s
        li
          & + li
            margin-top: $spacing
        .point_detail_block
          #total_point
            line-height: 18px
            .point_icon
              width: 18px
              height: 18px
              margin-right: $spacing*.4
            >span
              line-height: inherit
      &.before-signin
        &:hover
          .hidden_bar-user
            display: block

    .menu-item
      >a 
        color: $white
        line-height: 1.5
        display: block
        padding: $spacing*.8

</style>
