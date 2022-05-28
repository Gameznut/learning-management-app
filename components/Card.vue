<template>
  <div :class="`p-[1rem] rounded-xl w-[max-content] ${course.bgClass} card`">
    <div>
      <img
        :class="`w-[300px] h-[170px] rounded-xl p-4  ${course.imageClass}`"
        :src="require(`./icons/${course.image}.svg`)"
        alt=""
      />
    </div>
    <h1 class="text-[25px] my-[1rem] font-[700]">{{ course.name }}</h1>
    <h2 class="mb-[4rem]">12 Lessons</h2>
    <div class="flex justify-between items-center">
      <div class="flex justify-between">
        <div
          class="
            w-[2.6rem]
            h-[2.6rem]
            bg-[#c4c4c4]
            rounded-full
            overflow-hidden
          "
        >
          <img
            class="object-fit"
            src="https://images.unsplash.com/photo-1499996860823-5214fcc65f8f?crop=entropy&cs=tinysrgb&fm=jpg&ixlib=rb-1.2.1&q=60&raw_url=true&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NXx8aHVtYW58ZW58MHx8MHx8&auto=format&fit=crop&w=500"
            alt="person1"
          />
        </div>
        <div
          class="
            w-[2.6rem]
            h-[2.6rem]
            mx-[-.5rem]
            bg-[black]
            rounded-full
            overflow-hidden
          "
        >
          <img
            src="https://images.unsplash.com/photo-1554151228-14d9def656e4?crop=entropy&cs=tinysrgb&fm=jpg&ixlib=rb-1.2.1&q=60&raw_url=true&ixid=MnwxMjA3fDB8MHxzZWFyY2h8N3x8aHVtYW58ZW58MHx8MHx8&auto=format&fit=crop&w=500"
            alt="person2"
          />
        </div>
        <div
          class="
            w-[2.6rem]
            h-[2.6rem]
            bg-[#c4c4c4]
            rounded-full
            overflow-hidden
          "
        >
          <img
            src="https://images.unsplash.com/photo-1555952517-2e8e729e0b44?crop=entropy&cs=tinysrgb&fm=jpg&ixlib=rb-1.2.1&q=60&raw_url=true&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTF8fGh1bWFufGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=500"
            alt="person3"
          />
        </div>
      </div>
      <div>
        <div
          :class="`
            ${course.buttonClass}
            ${course.shadow}
            relative
            p-[1rem]
            flex
            justify-center
            items-center
            rounded-[.4rem]
            shadow-lg arrow`"
        >
          <Arrow />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Arrow from "./icons/Arrow.vue";
import Javascript from "./icons/Javascript.svg";
export default {
  components: { Arrow, Javascript },
  data() {
    return {
      Javascript: "Javascript",
    };
  },
  props: ["course"],
};
</script>
<style scoped>
.card {
  transition: 0.4s;
  cursor: pointer;
  box-shadow: 4px 4px 19px rgb(156, 156, 156);
}
.card:hover {
  transform: scale(1.05);
}
.arrow {
  transition: 0.4s;
}

.arrow:hover {
  cursor: pointer;
  transform: scale(1.09);
}
</style>