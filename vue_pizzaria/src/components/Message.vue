<template>
    <div class="message-container">
        <p>{{ msg }}</p>
    </div>
</template>

<script>
  export default {
    name: "Message",
    props: {
        msg:"string"
    },
  }
</script>

<style scoped>
  .message-container {
    color: #E6531D;
    background-color: #822300;
    border: 2px solid #E6531D;
    border-radius: 5px;
    padding: 10px;
    max-width: 400px;
    margin: 30px auto;
  }
</style>