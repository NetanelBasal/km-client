<template>

  <section class="flex">
    <div class="flex-one inbox">
      <inbox></inbox>
    </div>
    <div class="flex-two message">
      <message></message>
    </div>
  </section>

</template>

<script>
  import Inbox from "./Inbox";
  import Message from "./Message"

  export default {
    components: {
      "inbox"  : Inbox,
      "message": Message
    }
  }
</script>

<style scoped>
  .message {
    padding-left: 1em;
    border-left: 1px solid lightgray;
    max-height: 100vh;
    overflow-y: scroll;
  }

  .inbox {
    max-height: 100vh;
    max-width: 450px;
    overflow-y: scroll;
  }

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
