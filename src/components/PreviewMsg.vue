<template>
  <div class="msg" :class="{ read: message._data.Read }">
    {{message._data.Read}}
    <p class="topic">{{ message._data.ConversationTopic }}</p>
    <button @click="markAsRead">{{message._data.Read ? "UnRead" : "Read"}}</button>
  </div>
</template>

<script>
  export default {
    name: "preview-msg",
    props: ["message"],
    mounted() {
//      console.log(this.message._data.UnRead);

    },
    methods: {
      markAsRead() {
        console.log(this.message);
        this.message._data.Read = ! this.message._data.Read;
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 .msg {
   border-bottom: 1px solid blue;
   padding: 1em;
 }

  .read {
    background: green;
    color: #fff;
  }
</style>
