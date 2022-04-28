<template>
  <div class="chat-container">
    <div class="chat-window">
      <div class="message-field">
        <div v-for="m in messages" :key="m">{{ m }}</div>
      </div>
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "ChatContainer",
  props: ["messages"],
  mounted: function () {
    console.log(this.messages[0]);
  },
};
</script>

<style scoped>
.chat-container {
  position: absolute;
  display: flex;
  justify-content: center;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
.chat-window {
  display: flex;
  justify-content: center;
  background-color: green;
  position: relative;
  top: 8rem;
  width: 40%;
  height: 80%;
  border-radius: 10%;
}
.message-field {
  background-color: white;
  height: 90%;
  margin-top: 1rem;
  width: 90%;
  border: ridge;
  border-radius: 10%;
}
</style>
