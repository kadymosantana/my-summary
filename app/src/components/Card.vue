<script>
import { ref } from "vue";
import ProfileInfos from "./ProfileInfos.vue";
import NetworksList from "./NetworksList.vue";
import ProjectsList from "./ProjectsList.vue";
import SkillsList from "./SkillsList.vue";

export default {
  components: {
    ProfileInfos,
    NetworksList,
    ProjectsList,
    SkillsList,
  },

  setup() {
    const activeComponent = ref("SkillsList");

    return { activeComponent };
  },
};
</script>

<template>
  <div class="container">
    <ProfileInfos />
    <nav>
      <ul>
        <li
          @click="activeComponent = 'NetworksList'"
          :class="{ active: activeComponent === 'NetworksList' }"
        >
          Contatos
        </li>
        <li
          @click="activeComponent = 'SkillsList'"
          :class="{ active: activeComponent === 'SkillsList' }"
        >
          Conhecimentos
        </li>
        <li
          @click="activeComponent = 'ProjectsList'"
          :class="{ active: activeComponent === 'ProjectsList' }"
        >
          Projetos
        </li>
      </ul>
    </nav>
    <component :is="activeComponent">
      <NetworkList />
      <ProjectsList />
      <SkillsList />
    </component>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 320px;
  max-height: 600px;
  overflow: scroll;
  background: #22222a;
  color: #e5e5e5;
  border-radius: 16px;
  padding: 20px 20px 0 20px;
}

nav {
  width: 100%;
  font-size: 16px;
  font-weight: 500;
  border-bottom: 1px solid #44444a;
  padding-bottom: 10px;
  margin: 30px 0;
}

nav ul {
  display: flex;
  justify-content: center;
  gap: 20px;
}

nav ul li {
  position: relative;
  cursor: pointer;
}

li.active::after {
  content: "";
  display: block;
  position: absolute;
  top: 29px;
  background: #00e6f6;
  width: 100%;
  height: 3px;
  border-radius: 25px;
}
</style>
