<template>
  <div class="bg-color">
    <div class="logo-container">
      <div class="row">
        <div class="col-12">
          <img src="" alt="">
        </div>
      </div>
    </div>

    <div class="album-wrapper container">
      <div class="row gy-3">
        <div v-for= "album in albumList" :key= "album.title" class="col-lg-2 col-md-4 col-6 album me-4">
          <img class="img-fluid" :src= "album.poster" :alt= "album.title">
          <h4>{{album.title}}</h4>
          <p>{{ album.author }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'AlbumList',
  props: {
    msg: String
  },
  data : function (){
    return {
      albumList : []
    }
  },

  created: function () {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((response)=> {
      this.albumList = response.data.response.slice();
      console.log(this.albumList);
    }
    )
  }

}

</script>


<style scoped lang="scss">
@import "../style/fontandcolor.scss";
@import "../style/general.scss";

.bg-color{
  background-color: $mainColor;

  .logo-container{
    height: 80px;
    width: 100%;
    background-color: $headerColor;
  }

.album-wrapper{
  padding: 5rem 4rem;

  .album{
      background-color: $headerColor;

      img{
        padding: 1rem 1rem;
      }
  }
}
}


</style>
