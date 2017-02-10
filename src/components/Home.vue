<template>

  <section class="flex">
    <div class="flex-one" style="max-height: 100vh; overflow: scroll;">
      <inbox></inbox>
    </div>
    <div class="flex-two">
      <message></message>
    </div>
  </section>

</template>

<script>
  import Inbox from "./Inbox";
  import Message from "./Message"

  export default {
    components: {
      "inbox": Inbox,
      "message": Message
    },
    data () {
      return {
        msg: 'Welcome to Your Vue.js App'
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .flex {
    display: flex;
  }

  .flex-one {
    flex: 1;
  }

  .flex-two {
    flex: 2;
  }
</style>
