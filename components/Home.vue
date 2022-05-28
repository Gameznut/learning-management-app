<template>
  <div class="flex display">
    <!-- section 1 -->
    <div class="w-[calc(70%+61rem)] section1 py-[40px] px-[20px] bg-[#f5f0f0]">
      <div class="flex mb-[20px] justify-between">
        <div><h1 class="text-[2.5rem] font-[800]">Dashboard</h1></div>
        <div>
          <div
            class="
              relative
              bg-slate-200
              p-[.5rem]
              pb-[.2rem]
              rounded-[.4rem]
              shadow-lg shadow-slate-400/40
            "
          >
            <Bell /><span
              class="
                absolute
                bg-[purple]
                w-[12px]
                block
                top-[5px]
                border-[rgb(148
                163
                184
                /
                0.4)]
                border-[2px]
                right-[14px]
                h-[12px]
                rounded-full
              "
            />
          </div>
        </div>
      </div>
      <section class="mb-[1.8rem]">
        <h1 class="text-[1.6rem] font-[600] mb-[1rem]">New Courses</h1>
        <div class="flex justify-evenly card">
          <Card v-for="(course, i) in NewCourses" :key="i" :course="course" />
        </div>
      </section>
      <section>
        <div class="flex justify-between items-center">
          <h1 class="text-[2.5rem] font-[800]">My Courses</h1>
          <p class="text-[1rem] font-[500] text-[purple]">View All</p>
        </div>
        <Table
          :my-courses="myCourses"
        />
      </section>
    </div>
    <!-- section 2 -->
    <div class="w-[30%] section2 py-[40px] px-[20px]">
      <div class="profile_section">
        <div class="flex justify-between mb-[20px] items-center">
          <h1 class="text-[2rem] font-[800]">Profile</h1>
          <Bell
            class="
              p-[.5rem]
              pb-[.2rem]
              rounded-[.4rem]
              shadow-lg shadow-slate-400/40
            "
          />
        </div>
        <div class="flex flex-col gap-[.7rem] items-center">
          <div
            class="w-[8.5rem] h-[8.5rem] bg-black rounded-full overflow-hidden"
          >
            <img
              src="https://images.unsplash.com/photo-1555952517-2e8e729e0b44?crop=entropy&cs=tinysrgb&fm=jpg&ixlib=rb-1.2.1&q=60&raw_url=true&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTF8fGh1bWFufGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=500"
              alt=""
            />
          </div>
          <div>
            <h1 class="text-center name">Emmanuel Pablo</h1>
            <h2 class="text-center">Elementry</h2>
          </div>
        </div>
      </div>
      <div class="calendar_section">
        <Calendar />
      </div>
      <div class="homework_section">
        <h1 class="title">Homework progress</h1>
        <div
          class="flex justify-between course items-center"
          v-for="(homework, i) in homeWorks"
          :key="i"
        >
          <div class="flex items-center gap-4">
            <div class="relative">
              <div class="skill">
                <div
                  class="outer"
                  :style="{
                    background: `conic-gradient(
            #cc00ff ${homework.done * 3.6}deg,
            #d8d8d8 ${homework.done * 3.6}deg
          )`,
                  }"
                >
                  <div class="inner">
                    <div id="number">{{ homework.done }}</div>
                  </div>
                </div>
              </div>
            </div>
            <div class="">
              <h1 class="title">{{ homework.title }}</h1>
              <small class="task">{{ homework.task }} tasks</small>
            </div>
          </div>

          <div>
            <Arrow />
          </div>
        </div>
        <!-- <div class="flex justify-between course items-center">
          <div class="flex items-center gap-4">
            <div class="relative">
              <div class="skill">
                <div class="outer">
                  <div class="inner"><div id="number">0%</div></div>
                </div>
              </div>
            </div>
            <div class="">
              <h1 class="title">styling with css</h1>
              <small class="task">12 tasks</small>
            </div>
          </div>

          <div>
            <Arrow />
          </div>
        </div>
        <div class="flex justify-between course items-center">
          <div class="flex items-center gap-4">
            <div class="relative">
              <div class="skill">
                <div class="outer">
                  <div class="inner"><div id="number">0%</div></div>
                </div>
              </div>
            </div>
            <div class="">
              <h1 class="title">styling with css</h1>
              <small class="task">12 tasks</small>
            </div>
          </div>

          <div>
            <Arrow />
          </div>
        </div> -->
      </div>
    </div>
    <div
      class="
        absolute
        bottom-[2rem]
        right-[2rem]
        hover:scale-[1.07]
        duration-300
        cursor-pointer
      "
    >
      <div
        class="
          relative
          p-[1rem]
          flex
          justify-center
          items-center
          rounded-[.4rem]
          arrow
          text-white
          bg-[#a3a3a3]
          -rotate-90
          shadow-lg shadow-stone-400
        "
      >
        <Arrow />
      </div>
    </div>
  </div>
</template>
<script>
import Bell from "./icons/Bell.vue";
import Card from "./Card.vue";
import Table from "./Table.vue";
import Calendar from "./Calendar.vue";
import Arrow from "./icons/Arrow.vue";
export default {
  data() {
    return {
      NewCourses: [
        {
          name: "Python",
          image: "Javascript",
          imageClass: "bg-[#FFE022]",
          bgClass: "bg-[#ffe082]",
          buttonClass: "bg-[#ffe182]",
          shadow: "shadow-[#cfc357]",
        },
        {
          name: "Javascript",
          image: "Javascript",
          imageClass: "bg-[#FFE022]",
          bgClass: "bg-[#ffe082]",
          buttonClass: "bg-[#ffe182]",
          shadow: "shadow-[#cfc357]",
        },
        {
          name: "Html",
          image: "Javascript",
          imageClass: "bg-[#f06529]",
          bgClass: "bg-[#f08029]",
          buttonClass: "bg-[#f16529]",
          shadow: "shadow-[#f76580]",
        },
      ],
      homeWorks: [
        { done: 9, task: 4, title: "Css syntax" },
        {
          done: 80,
          task: 14,
          title: "Html syntax",
        },
        {
          done: 80,
          task: 10,
          title: "Python syntax",
        },
      ],
      myCourses: [
        {
          name: "Css Syntax",
          start: "May 14",
          rate: "4.6",
          level: "Elementry",
          lesson: "10 lessons",
        },
        {
          name: "Html Syntax",
          start: "May 14",
          rate: "4.6",
          level: "Elementry",
          lesson: "10 lessons",
        },
        {
          name: "Php Syntax",
          start: "May 14",
          rate: "4.6",
          level: "Elementry",
          lesson: "10 lessons",
        },
        {
          name: "Firebase Syntax",
          start: "May 14",
          rate: "4.6",
          level: "Elementry",
          lesson: "10 lessons",
        },
        {
          name: "Mongo Syntax",
          start: "May 14",
          rate: "4.6",
          level: "Elementry",
          lesson: "10 lessons",
        },
      ],
    };
  },
  components: {
    Bell,
    Card,
    Table,
    Calendar,
    Arrow,
  },
  methods: {},
  mounted() {
    if (process.browser) {
      // let progressbar = document.querySelectorAll(".outer");
      // let number = document.querySelectorAll("#number");
      // let test = [];
      // let progressValue = 0;
      // let progressEndValue = 90;
      // let speed = 50;
      // // for (const a of this.homeWorks) {
      // //   console.log(a.task);
      // // }
      // test.push(progressbar);
      // this.homeWorks.forEach((e, i) => {
      //   // console.log(e, i);
      //   // progressbar.forEach((bar) => {
      //   //   bar.style.background = `conic-gradient(
      //   //     #cc00ff ${i * 3.6}deg,
      //   //     #d8d8d8 ${i * 3.6}deg
      //   //   )`;
      //   //   bar.style.background = `conic-gradient(
      //   //     #cc00ff ${i * 3.6}deg,
      //   //     #d8d8d8 ${i * 3.6}deg
      //   //   )`;
      //   // });
      // });
      // // let progress = setInterval(() => {
      // //   progressValue++;
      // //   number.forEach((num) => {
      // //     num.textContent = `${progressValue}%`;
      // //   });
      // //   progressbar.forEach((bar) => {
      // //     bar.style.background = `conic-gradient(
      // //       #cc00ff ${progressValue * 3.6}deg,
      // //       #d8d8d8 ${progressValue * 3.6}deg
      // //     )`;
      // //   });
      // //   this.homeWorks.forEach((e) => {
      // //     console.log(e.task);
      // //     if (progressValue == e.done) {
      // //       clearInterval(progress);
      // //     }
      // //   });
      // // }, speed);
    }
  },
};
</script>

<style scoped>
.profile_section .name {
  font-size: 1.2rem;
  font-weight: 800;
}
.homework_section .title {
  font-size: 1.4rem;
  font-weight: 800;
}

.course {
  background-color: #fff;
  border-radius: 0.5rem;
  margin: 1rem 0;
  cursor: pointer;
  padding: 1rem;
  transition: 0.4s;
  box-shadow: 2px 2px 4px rgb(172, 170, 170);
  /* transform: scale(0.9); */
}

.course .title {
  font-size: 16px;
  font-weight: 600;
  text-transform: capitalize;
}

.course .task {
  font-size: 12px;
}

.course:hover {
  background-color: rgb(105, 46, 105);
  color: #fff;
  transform: scale(1.05);
}

.skill {
  width: 60px;
  height: 60px;
  position: relative;
}
/* Apply css properties to outer class */
.outer {
  width: 60px;
  height: 60px;
  border-radius: 9rem;
  display: flex;
  justify-content: center;
  position: relative;
  align-items: center;
}

.outer::before {
  position: absolute;
  content: "";
  width: calc(50px);
  height: 50px;
  border-radius: 9rem;
  display: flex;
  justify-content: center;
  background: #ffffff;
  align-items: center;
  z-index: 0;
}
#number {
  position: relative;
  z-index: 1;
  color: black;
}

@media screen and (max-width: 800px) {
  .display {
    flex-direction: column;
    overflow: hidden;
    margin-left: 76px;
  }
  .section1,.section2{
    width: 100%;
  }
  .card{
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }
}
</style>