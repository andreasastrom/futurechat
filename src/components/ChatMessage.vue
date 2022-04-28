<template>
  <div class="message-container">
    <p class="sender">{{ sender }}</p>
    <p class="message">{{ message }}</p>
  </div>
</template>

<script>
export default {
  props: {
    sender: String,
    message: String,
  },
};
</script>

<style>
.message-container {
  height: 4rem;
  display: inline-block;
  flex-direction: column;
  margin-bottom: 1rem;
}
.sender {
  margin: 0 0.5rem;
  text-align: left;
  font-family: "Arial Narrow", sans-serif;
  font-size: 0.825rem;
  align-self: flex-start;
}

.message {
  border: #81b29a 1px solid;
  line-height: 1rem;
  background-color: #81b29a;
  border-radius: 15px;
  width: 60%;
  padding: 0;
  font-family: "Arial", sans-serif;
  font-size: 1rem;
}
</style>
