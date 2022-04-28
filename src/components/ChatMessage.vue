<template>
  <p class="sender">{{ sender }}</p>
  <p class="message">{{ message }}</p>
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
.sender {
  margin: 0 0.7rem;
  text-align: left;
  font-family: "Arial Narrow", sans-serif;
  font-size: 0.825rem;
}

.message {
  padding: 0.5rem;
  border: #81b29a 1px solid;
  background-color: #81b29a;
  border-radius: 15px;
  width: 25%;
  margin: 0;
  font-family: "Arial", sans-serif;
  font-size: 1rem;
}
</style>
