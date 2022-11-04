<script>
export default {
  setup() {},
};
</script>

<template>
  <div>
    <img src="../../public/assets/profile.jpeg" alt="Kádymo Santana" />
    <h1>Kádymo Santana</h1>
    <p>Desenvolvedor Front-end</p>
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  align-items: center;
}

img {
  max-width: 140px;
  border-radius: 50%;
  filter: drop-shadow(0px 3px 10px #11111a);
  margin-bottom: 10px;
}

h1 {
  font-size: 1.7rem;
  font-weight: 600;
  letter-spacing: -1px;
  margin-bottom: 5px;
}

p {
  color: #999;
}
</style>
