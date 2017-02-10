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
//      setInterval(() => {
//        axios.get('http://localhost:3000').then(res => {
//          this.messages = this.messages.concat(res.data);
//        });
//      }, 3000)
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
