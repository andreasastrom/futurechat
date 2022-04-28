<template>
  <p class="chat-title">Awesome Chat</p>
  <div class="chat-container">
    <div class="chat-window">
      <div class="message-field">
        <ChatMessage
          v-for="m in messages"
          :key="m"
          class="message"
          :message="m.message"
          :sender="m.sender"
        />
      </div>
    </div>
  </div>
</template>

<script>
import ChatMessage from "./ChatMessage.vue";

export default {
  name: "ChatContainer",
  data: () => ({
    messages: [
      {
        sender: "Mr. Test",
        message: "Test Message",
      },
    ],
    wsUri: "ws://192.168.2.127:5002/ws",
    ws: {},
    currMessage: "Initial Message",
  }),
  props: ["currSender"],
  components: {
    ChatMessage,
  },
  watch: {
    currMessage: {
      handler() {
        const inputMessage = {
          sender: this.currSender,
          message: this.currMessage,
        };
        this.messages.push(inputMessage);
      },
      immediate: true,
    },
  },
  mounted: () => {
    this.ws = new WebSocket(this.wsUri);
    this.ws.onmessage = (event) => {
      this.currMessage = event.data;
    };
  },
};
</script>

<style scoped>
.chat-title {
  color: green;
}

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
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: center;
  background-color: white;
  height: 90%;
  margin-top: 1rem;
  width: 90%;
  border: ridge;
  border-radius: 10%;
  overflow: scroll;
}
</style>
