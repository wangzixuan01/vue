<template>
  <div class="detail">
    <common-header title="detail" bgColor="rgb(33, 150, 243)" nav="<">
    </common-header>
    <div class="det">
      <v-touch class="photo-detail" :style="{background:bg}"
        @swipeleft="left"  @swiperight="right">
      </v-touch>

    </div>
  </div>
</template>

<script>
  import CommonHeader from "../common/CommonHeader.vue"
  import {mapState} from 'vuex';
  import  Axios from 'axios'

  export default {

    data(){
      return{
        aa:this.$route.params.index
      }
    },
    computed:{
      bg(){
        return "url("+ this.$store.state.photoData[this.aa].src +") no-repeat center / contain #000"
      },
      ...mapState(["photoData"])
    },
    methods:{
      left(){
        this.aa++;
      },
      right(){
        this.aa--;
      }
    },
    components:{
      CommonHeader
    }
  }
</script>

<style>
.photo-detail{
  position: absolute;
  top:1rem;
  bottom: 0;
  width: 100%;
}
</style>
