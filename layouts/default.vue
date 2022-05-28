<template>
  <div id="app">
    <Navigation class="nav bg-[#dfdbdb]" />
    <Nuxt class="w-full h-[max-content] display" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      scrollPosition: false,
      shiftPosition: false,
    };
  },
  mounted() {},
  methods: {
    updateScroll() {
      const scrolled = window.scrollY;
      console.log(scrolled);
      if (scrolled > 1) {
        return (this.scrollPosition = true);
      }
      this.scrollPosition = false;
      return;
    },
    shiftDisplay(e) {
      const scrolled = window.scrollY;
      if (scrolled == 0) {
        return (this.scrollPosition = false), (this.shiftPosition = false);
      } else {
        this.shiftPosition = true;
        // e.target.style.margin-left = '250px'
        return;
      }
    },
  },
};
</script>

<style scoped>
#app {
  display: flex;
  position: relative;
}
.nav {
  width: 100%;
  overflow: hidden;
  transition: 0.4s;
  max-width: 76px;
  padding: 0 0.5rem;
}
.nav:hover {
  max-width: 250px;
}

</style>