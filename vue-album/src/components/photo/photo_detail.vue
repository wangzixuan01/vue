<template>
  <div class="detail">
    <div v-for="">
    <img :src="obj.src[index]" alt="">
    </div>
  </div>
</template>

<script>
  import CommonHeader from "../common/CommonHeader.vue"
  import  Axios from 'axios'

  export default {

    data(){
      return{
        photoData:[]
      }
    },
    mounted(){
      Axios.get('/static/photo-data.json')
        .then((res)=>{
        this.photoData = res.data.photoData;
        })
    }


  }



</script>
