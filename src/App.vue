<template>
  <div id="app">
    <AlbumList msg=""/>
  </div>
</template>

<script>
import AlbumList from './components/AlbumList.vue'

export default {
  name: 'App',
  components: {
    AlbumList
  }
}
</script>

<style lang="scss">
@import './style/general.scss';
@import './style/fontandcolor.scss';


#app {
  
}
</style>
