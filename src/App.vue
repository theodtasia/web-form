<template>
  <Form />
</template>

<script>
import Form from "./components/Form.vue";

export default {
  name: "App",
  components: { Form },
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  text-align: center;
  color: #265483;
  margin-top: 60px;
}
body {
  margin: 0;
  background: #eee;
}
</style>
