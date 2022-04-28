<template>
  <ChatMessage
    sender="Victor"
    message="Hello there, this is a longer message, looking forward to lunch!"
  />
</template>

<script>
import ChatMessage from "../src/components/ChatMessage.vue";

export default {
  components: { ChatMessage },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
