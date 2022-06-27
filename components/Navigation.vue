<template>
  <header class="">
    <nav>
      <div class="logo"></div>
      <div>
        <ul>
          <li>
            <NuxtLink class="link" to="/"
              ><span class="w-[30px] inline-block "><Dashboard /> </span>
              Dashboard</NuxtLink
            >
          </li>
          <li>
            <NuxtLink class="link" to="/courses"
              ><span class="w-[30px] inline-block"><Courses class="" /> </span>
              Courses</NuxtLink
            >
          </li>
          <li>
            <NuxtLink class="link" to="#"
              ><span class="w-[30px] inline-block"><Grades /> </span>
              Grades</NuxtLink
            >
          </li>
          <li>
            <NuxtLink class="link" to="#"
              ><span class="w-[30px] inline-block"><Schedule /> </span>
              Schedule</NuxtLink
            >
          </li>
          <li>
            <NuxtLink class="link" to="#"
              ><span class="w-[30px] inline-block"><Settings /> </span>
              Settings</NuxtLink
            >
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>
<script>
import Dashboard from "./icons/Dashboard.vue";
import Courses from "./icons/Courses.vue";
import Grades from "./icons/Grades.vue";
import Schedule from "./icons/Schedule.vue";
import Settings from "./icons/Settings.vue";
export default {
  components: {
    Dashboard,
    Courses,
    Grades,
    Schedule,
    Settings,
  },
  setup() {
    return {};
  },
};
</script>
<style scoped>
.logo {
  margin: 4rem 0;
}

.link {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 0.5rem 1rem;
  transition: 0.4s;
}
.link:hover {
  color: rgba(228, 228, 228, 0.945);
  background-color: #9e9e9e;
  border-radius: 0.5rem;
}
.link span {
  margin-right: 0.3rem;
}
ul {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
header:hover {
  color: rgba(121, 121, 121, 0.945);
}
header {
  color: rgba(121, 121, 121, 0.945);

}
/* .nuxt-link-active {
  color: rgba(0, 0, 0, 0);
  /* color: red; 
}*/
.nuxt-link-exact-active {
  border-right: #3ece05 solid 4px;
}
.nuxt-link-exact-active:hover {
  border-right: #3ece0500 solid 2px;
}

@media screen and (max-width: 800px) {
  header {
    position: fixed;
    top: 0;
    left: 0;
    height: 100vh;
    z-index: 999;
  }
}
</style>