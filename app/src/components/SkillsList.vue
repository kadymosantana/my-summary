<script>
import skills from "../data/skills.json";

export default {
  setup() {
    return { skills };
  },
};
</script>

<template>
  <ul class="skills" v-once>
    <li class="skill" v-for="skill in skills" :key="skill.name">
      <div class="img-container" :style="{ background: skill.background }">
        <img :src="skill.img" :alt="skill.name" />
      </div>
      <div>
        <h2>{{ skill.name }}</h2>
        <p>{{ skill.description }}</p>
      </div>
    </li>
  </ul>
</template>

<style scoped>
.skills {
  display: flex;
  flex-direction: column;
  height: 400px;
  overflow: scroll;
}

.skills .skill:last-child {
  padding-bottom: 20px;
}

.skill {
  display: grid;
  grid-template-columns: auto 1fr;
  align-items: center;
  gap: 20px;
  border-radius: 12px;
  padding: 10px 0;
}

.skill:nth-child(1) {
  padding-top: 0;
}

.skill .img-container {
  display: flex;
  border-radius: 12px;
  padding: 12px;
}

.skill img {
  width: 20px;
}

.skill h2 {
  font-size: 1rem;
  font-weight: 500;
  margin-bottom: 3px;
}

.skill p {
  font-size: 14px;
  letter-spacing: -0.3px;
  color: #999;
}
</style>
