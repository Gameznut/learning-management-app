<template>
  <div>
    <table class="w-full">
      <thead>
        <tr class=" font-[900] text-[gray] text-left gap-4">
          <th class="w-[55%]">Course Name</th>
          <th class="w-[15%] text-left">Start</th>
          <th class="w-[15%] text-center">Rate</th>
          <th class="w-[15%] text-center">Level</th>
        </tr>
      </thead>

      <tbody>
        <tr     v-for="(mycourse, i) in myCourses"
          :key="i" class=" font-[700] p-2 pl-0 items-center gap-4">
          <td class="w-[55%] flex gap-4 items-center">
            <span
              ><Bell
                class="
                  w-[50px]
                  h-[50px]
                  bg-slate-400
                  p-2
                  rounded-xl
                  inline-block
                "
            /></span>
            <div class="flex flex-col">
              <h1 class="">{{ mycourse.name }}</h1>
              <small class="text-[gray] text-xs">{{ mycourse.lesson }}</small>
            </div>
          </td>
          <td class="w-[15%] text-left">{{ mycourse.start }}</td>
          <td class="w-[15%] text-center">{{ mycourse.rate }}</td>
          <td class="w-[15%] text-center">{{ mycourse.level }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
import Bell from "./icons/Bell.vue";
export default {
  components: {
    Bell,
  },
  props: ["my-courses"],
};
</script>
<style scoped>

@media screen and (max-width: 600px) {

}</style>