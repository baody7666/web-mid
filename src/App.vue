<template lang="pug">
  #app
    //-#nav
      //-router-link(to="/") Home |
      //-router-link(to="/about") About
    .menuFlex 
     .search
      .searchIcon
     .menuList
       .menu(v-for="item in menuList")    
        .menuItem {{item.title}}
        //- .secondaryMenu
        div(:class="item.isTrue==true? 'secondaryMenu':'noMenu'")
          .secondary(v-for="option in item.secondary") {{option}}
    router-view
</template>
<script>
export default {
  data(){
    return{
      menuList: [
        {title: 'Home'},
        {title: 'News'},
        {title: 'Admission',secondary: ['春之清華獎學金','FB粉絲團','2020招生','招生Q&A'],isTrue: true},
        {title: 'Teachers',secondary: ['學士班','藝設系','音樂系','電資學院',],isTrue: true},
        {title: 'Contact'}
      ]
    }
  }
}
</script>
<style lang="sass">
@font-face 
  font-family: "GemunuLibre-Medium"
  src: local("GemunuLibre-Medium"),url("./fonts/ttf/GemunuLibre-Light.ttf") format("truetype")
#app 
  font-family: Avenir, Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  text-align: center
  color: #2c3e50
  display: flex
  flex-direction: row-reverse

#nav 
  padding: 30px


#nav a 
  font-weight: bold
  color: #2c3e50

#nav a.router-link-exact-active 
  color: #42b983

.menuFlex
  width: 150px
  height:1080px
  background-color: #FFF
  overflow: visible
  z-index: 1000
.search
  padding: 35px 50px
  background-color: #5D6874

.searchIcon
  width: 50px
  height:50px
  background-image: url("https://www.flaticon.com/svg/static/icons/svg/622/622669.svg")
  background-size: cover

.menu
  // display: flex
  // flex-direction: row-reverse
  position: relative
  cursor: pointer
.menu:hover
  .secondaryMenu
    display: block
    display: flex
    flex-direction: column
    justify-content: space-around
.menuItem
  writing-mode: vertical-lr
  text-orientation: mixed
  font-size: 30px

.menuList
  display: flex
  flex-direction: column
  justify-content: space-around
  height: 960px
  align-items: center
  overflow: visible
.secondaryMenu
  width: 320px
  height: 100%
  position: absolute
  right: 34.67px
  top: 0px
  display: none
  font-family: HammersmithOne
  font-style: normal
  font-weight: normal
  font-size: 24px
  line-height: 30px
  text-align: left
  letter-spacing: 0.1em
  background-color: #5D6874
  color: #fff
</style>
