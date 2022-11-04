<script>
import networks from "../data/networks.js";
export default {
  setup() {
    return { networks };
  },
};
</script>

<template>
  <ul class="networks" v-once>
    <li class="network" v-for="network in networks" :key="network.name">
      <a :href="network.url" target="_blank">
        <div class="img-container" :style="{ background: network.background }">
          <img :src="network.img" :alt="network.name" />
        </div>
        <div>
          <h2>{{ network.name }}</h2>
          <p>{{ network.description }}</p>
        </div>
      </a>
    </li>
  </ul>
</template>

<style scoped>
.networks {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 400px;
  color: #321a36a6;
}

.network a {
  display: grid;
  grid-template-columns: auto 1fr;
  align-items: center;
  gap: 20px;
  width: 100%;
  color: #e5e5e5;
  border-radius: 12px;
  padding: 10px 0;
}

.network:nth-child(1) a {
  padding-top: 0;
}

.network a .img-container {
  display: flex;
  border-radius: 12px;
  padding: 12px;
}

.network a img {
  width: 20px;
}

.network a h2 {
  font-size: 1rem;
  font-weight: 500;
  margin-bottom: 3px;
}

.network a p {
  font-size: 14px;
  color: #999;
}
</style>
