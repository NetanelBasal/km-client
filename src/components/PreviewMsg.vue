<template>
  <div class="msg" :class="{ read: message._data.read, flex: true }" @click="markAsRead">

    <p :class="{c: message._data.read,  indication: true}">
      &#9679;
    </p>

    <div class="left">
      <p class="from">{{message._data.From}}</p>
      <p class="topic">{{message._data.topic}}</p>
      <p class="summary">{{message._data.summary}}</p>
    </div>

    <div class="right flex-one">
      {{message._data.date}}
    </div>

  </div>
</template>

<script>
  import * as axios from "axios";
  export default {
    name   : "preview-msg",
    props  : ["message"],
    methods: {
      markAsRead() {
        this.message._data.read = !this.message._data.read;
        axios.get('http://localhost:3000/mail').then(res => {
          this.$store.commit("updateMessage", res.data);
        });
      }
    }
  }
</script>

<style scoped>
  .indication {
    color: darkgrey;
    margin-right: 0.5em;
  }

  .left {
    flex: 0 1 350px;
  }

  .msg {
    padding: 0.6em 0.2em 0.6em 0.5em;
    border-bottom: 1px solid lightgray;
    cursor: pointer;
  }

  .from {
    font-size: 1rem;
    margin-bottom: 0.2em;
  }

  .topic {
    font-size: 0.8rem;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    width: 300px;
    margin-bottom: 0.2em;
  }

  .summary {
    font-size: 0.7rem;
    color: grey;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    width: 300px;
  }

  .read {
    background: lightblue;
  }

  .c {
    color: orange;
  }

  .right {
    font-size: 0.7rem;
    color: grey;
    padding-right: 0.5em;
  }

  .flex-two {
    flex: 2;
  }
</style>
