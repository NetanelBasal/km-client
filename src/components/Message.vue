<template>
  <section>
    <div class="head">
      <p class="date"> {{ currentMessage.date }}</p>
      <p class="from"> {{ currentMessage.from }}</p>
      <p class="topic"> {{currentMessage.topic}}</p>
    </div>

    <div class="body flex">
      <p class="img"><img src="https://www.gravatar.com/avatar?monsterid" alt=""></p>
      <section class="right">
        <div class="flex flex-one top-actions">
          <p style="font-weight: bold;">{{currentMessage.from}}</p>
          <p class="grey">{{currentMessage.date}}</p>
          <button class="grey">Delete</button>
          <button class="grey">Pop Out</button>
        </div>
        <p class="to"><span style="font-weight: bold;">To:</span> {{currentMessage.to}}</p>
        <div v-html="currentMessage.body"></div>
      </section>
    </div>

    <textarea name="" id="" cols="30" rows="10" style="width: 100%" placeholder="Reply"></textarea>

  </section>

</template>

<script>

  export default {
    computed: {
      currentMessage() {
        return this.$store.state.currentMessage;
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  textarea {
    padding: 1em;
    font-size: 1.2rem !important;
  }
  .body {
    margin: 0.6em 0;
  }

  .img {
    flex: 0 0 80px;
  }

  .img img {
    width: 50px;
    height: 50px;
  }

  .top-actions {
    margin-bottom: 0.4em;
  }

  button {
    padding: 0.3em;
  }

  .top-actions p {
    margin-right: 0.7em;
    font-size: 0.9rem;
  }

  .head {
    padding: 0.4em 0.4em 0.4em;
    border-bottom: 1px solid lightgray;
  }

  .date {
    color: grey;
    font-size: 0.8rem;
    margin-bottom: 0.3em;
  }

  .from {
    font-size: 1.4rem;
    color: grey;
    font-weight: 100;
    margin-bottom: 0.1em;
  }

  .topic {
    font-weight: 500;
    font-size: 0.9rem;
  }

  .to {
    margin-bottom: 0.5em;
  }
</style>
