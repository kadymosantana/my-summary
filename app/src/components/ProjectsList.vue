<script>
import projects from "../data/projects.js";

export default {
  setup() {
    return { projects };
  },
};
</script>

<template>
  <ul class="projects" v-once>
    <li class="project" v-for="project in projects" :key="project">
      <img :src="project.img" :alt="project.name" />
      <h1>{{ project.name }}</h1>
      <p>{{ project.description }}</p>

      <ul>
        <li v-for="tool in project.tools" :key="tool">
          {{ tool }}
        </li>
      </ul>
      <div class="links">
        <a :href="project.repository_url">
          <svg width="18" height="18" viewBox="0 0 256 250">
            <path
              fill="#fff"
              d="M128.001 0C57.317 0 0 57.307 0 128.001c0 56.554 36.676 104.535 87.535 121.46c6.397 1.185 8.746-2.777 8.746-6.158c0-3.052-.12-13.135-.174-23.83c-35.61 7.742-43.124-15.103-43.124-15.103c-5.823-14.795-14.213-18.73-14.213-18.73c-11.613-7.944.876-7.78.876-7.78c12.853.902 19.621 13.19 19.621 13.19c11.417 19.568 29.945 13.911 37.249 10.64c1.149-8.272 4.466-13.92 8.127-17.116c-28.431-3.236-58.318-14.212-58.318-63.258c0-13.975 5-25.394 13.188-34.358c-1.329-3.224-5.71-16.242 1.24-33.874c0 0 10.749-3.44 35.21 13.121c10.21-2.836 21.16-4.258 32.038-4.307c10.878.049 21.837 1.47 32.066 4.307c24.431-16.56 35.165-13.12 35.165-13.12c6.967 17.63 2.584 30.65 1.255 33.873c8.207 8.964 13.173 20.383 13.173 34.358c0 49.163-29.944 59.988-58.447 63.157c4.591 3.972 8.682 11.762 8.682 23.704c0 17.126-.148 30.91-.148 35.126c0 3.407 2.304 7.398 8.792 6.14C219.37 232.5 256 184.537 256 128.002C256 57.307 198.691 0 128.001 0Zm-80.06 182.34c-.282.636-1.283.827-2.194.39c-.929-.417-1.45-1.284-1.15-1.922c.276-.655 1.279-.838 2.205-.399c.93.418 1.46 1.293 1.139 1.931Zm6.296 5.618c-.61.566-1.804.303-2.614-.591c-.837-.892-.994-2.086-.375-2.66c.63-.566 1.787-.301 2.626.591c.838.903 1 2.088.363 2.66Zm4.32 7.188c-.785.545-2.067.034-2.86-1.104c-.784-1.138-.784-2.503.017-3.05c.795-.547 2.058-.055 2.861 1.075c.782 1.157.782 2.522-.019 3.08Zm7.304 8.325c-.701.774-2.196.566-3.29-.49c-1.119-1.032-1.43-2.496-.726-3.27c.71-.776 2.213-.558 3.315.49c1.11 1.03 1.45 2.505.701 3.27Zm9.442 2.81c-.31 1.003-1.75 1.459-3.199 1.033c-1.448-.439-2.395-1.613-2.103-2.626c.301-1.01 1.747-1.484 3.207-1.028c1.446.436 2.396 1.602 2.095 2.622Zm10.744 1.193c.036 1.055-1.193 1.93-2.715 1.95c-1.53.034-2.769-.82-2.786-1.86c0-1.065 1.202-1.932 2.733-1.958c1.522-.03 2.768.818 2.768 1.868Zm10.555-.405c.182 1.03-.875 2.088-2.387 2.37c-1.485.271-2.861-.365-3.05-1.386c-.184-1.056.893-2.114 2.376-2.387c1.514-.263 2.868.356 3.061 1.403Z"
            />
          </svg>
          Repositório</a
        >
        <a :href="project.demo_url">
          <svg width="20" height="20" viewBox="0 0 256 256">
            <path
              fill="#fff"
              d="M80 232a15.5 15.5 0 0 1-7.8-2.1A15.8 15.8 0 0 1 64 216V40a15.8 15.8 0 0 1 8.2-13.9a15.5 15.5 0 0 1 16.1.3l144 87.9a16 16 0 0 1 0 27.4l-144 87.9A15.4 15.4 0 0 1 80 232Zm0-192v176l144-88Z"
            />
          </svg>

          Demo</a
        >
      </div>
    </li>
    <a
      class="view-all"
      href="https://github.com/kadymosantana?tab=repositories"
      target="_blank"
    >
      Ver todos
      <svg width="20" height="20" viewBox="0 0 256 256">
        <path
          fill="#e5e5e5"
          d="m221.7 133.7l-72 72a8.2 8.2 0 0 1-11.4 0a8.1 8.1 0 0 1 0-11.4l58.4-58.3H40a8 8 0 0 1 0-16h156.7l-58.4-58.3a8.1 8.1 0 0 1 11.4-11.4l72 72a8.1 8.1 0 0 1 0 11.4Z"
        />
      </svg>
    </a>
  </ul>
</template>

<style scoped>
.projects {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
  height: 400px;
  list-style: none;
  overflow: scroll;
  padding-bottom: 20px;
}

.project {
  display: flex;
  flex-direction: column;
  gap: 10px;
  background: #33333a;
  border-radius: 16px;
  padding: 20px;
}

.project img {
  max-width: 100%;
  border-radius: 12px;
  margin-bottom: 10px;
}

.project h1 {
  font-size: 1.4rem;
  font-weight: 600;
}

.project ul {
  display: flex;
  flex-wrap: wrap;
  gap: 5px;
}

.project p,
.project ul li {
  font-size: 15px;
  letter-spacing: -0.3;
}

.project ul li {
  display: flex;
  background: #22222a;
  border-radius: 10px;
  padding: 6px 12px;
}

.project .links {
  display: flex;
  gap: 10px;
  padding-top: 15px;
}

.project .links a {
  display: flex;
  align-items: center;
  gap: 8px;
  background: #888;
  color: #fff;
  border-radius: 10px;
  padding: 6px 12px;
}

.project .links a:hover {
  transition: .3s;
  box-shadow: 0px 3px 5px #444;
}

.view-all {
  display: flex;
  align-items: center;
  gap: 5px;
  font-size: 1rem;
  color: #e5e5e5;
  border: 1px solid #e5e5e5;
  border-radius: 25px;
  padding: 8px 16px;
}

.view-all:hover svg {
  transition: 0.3s;
  transform: translateX(3px);
}
</style>
