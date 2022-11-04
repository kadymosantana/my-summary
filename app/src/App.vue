<script>
import Card from "./components/Card.vue";
export default {
  components: {
    Card,
  },
};
</script>

<template>
  <Card />
</template>

<style>
* {
  padding: 0;
  margin: 0;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
  background: linear-gradient(to top right, #11111a, #22222a);
  font-family: "Inter", sans-serif;
  letter-spacing: -0.5px;
}

ul {
  list-style: none;
}

a {
  text-decoration: none;
}
</style>
