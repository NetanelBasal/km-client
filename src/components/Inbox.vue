<template>
  <div>
    <preview-msg v-for="msg in messages" :message="msg"></preview-msg>
  </div>
</template>

<script>
  import PreviewMsg from "./PreviewMsg";
  import * as axios from "axios";

  export default {
    components: {
      "preview-msg": PreviewMsg
    },
    mounted() {
      axios.get('http://localhost:3000').then(res => {
        this.messages = this.messages.concat(res.data);
      });
//      const interval = setInterval(() => {
//        axios.get('http://localhost:3000').then(res => {
//          this.messages = this.messages.concat(res.data);
//          console.log(this.messages.length);
//
//          if( this.messages.length > 5000 ) {
//            clearInterval(interval);
//          }
//
//        });
//      }, 1000)
    },
    data () {
      return {
        messages: []
      }
    }
  }
</script>

<style scoped>

</style>
