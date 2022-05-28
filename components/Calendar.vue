<template>
  <div class="container">
    <vc-calendar
      class="bg-red-500"
      :attributes="attributes"
      :value="null"
  
      color="yellow"
      title-position="left"
      is-expanded
    />
  </div>
</template>

<script>
export default {
  data() {
    const date = new Date();
    const year = date.getFullYear();
    const month = date.getMonth();
    return {
      attributes: [
        // This is a single attribute
        {
          // An optional key can be used for retrieving this attribute later,
          // and will most likely be derived from your data object
          key: "today",
          // Attribute type definitions
          highlight: {
            color: "orange",
            fillMode: "outline",
          },
          content: "yellow",
          dates: new Date(),
          order: 0,
        },
        {
          key: "today",
          highlight: {
            color: "purple",
            fillMode: "light",
            contentClass: "italic",
          },
          popover: {
            label: "Python",
          },
          dates: { weekdays: 6 },
        },
        {
          highlight: {
            color: "purple",
            fillMode: "light",
          },
          popover: {
            label: "Html",
          },
          dates: new Date(year, month, 13),
        },
        {
          highlight: {
            color: "purple",
            fillMode: "outline",
          },
          dates: new Date(year, month, 14),
        },
        {
          dot: true,
          popover: {
            label: "Java",
          },
          dates: [
            new Date(year, month, 1), // Jan 1st
            new Date(year, month, 24), // Jan 10th
            new Date(year, month, 31), // Jan 22nd
          ],
        },
        {
          dot: "yellow",
          dates: [
            new Date(year, month, 2), // Jan 1st
            new Date(year, month, 25), // Jan 10th
            new Date(year, month, 31), // Jan 22nd
          ],
        },
        {
          dot: "green",
          dates: [
            new Date(year, month, 2), // Jan 1st
            new Date(year, month, 25), // Jan 10th
            new Date(year, month, 31), // Jan 22nd
          ],
        },
        {
          dot: "blue",
          dates: [
            new Date(year, month, 2), // Jan 1st
            new Date(year, month, 25), // Jan 10th
            new Date(year, month, 31), // Jan 22nd
          ],
        },
        {
          highlight: {
            start: { fillMode: "outline" },
            base: { fillMode: "light" },
            end: { fillMode: "outline" },
          },
          popover: {
            label: "Java",
          },
          dates: {
            start: new Date(year, month, 2),
            end: new Date(year, month, 12),
          },
        },
      ],
    };
  },
  //   computed: {
  //     dates() {
  //       return this.days.map((day) => day.date);
  //     },
  //     attributes() {
  //       return this.dates.map((date) => ({
  //         highlight: true,
  //         dates: date,
  //       }));
  //     },
  //   },
  //   methods: {
  //     onDayClick(day) {
  //       const idx = this.days.findIndex((d) => d.id === day.id);
  //       if (idx >= 0) {
  //         this.days.splice(idx, 1);
  //       } else {
  //         this.days.push({
  //           id: day.id,
  //           date: day.date,
  //         });
  //       }
  //     },
  //   },
};
</script>

<style>
.container {
  padding: 1.5rem 0 ;
}
.container .vc-container {
  background-color: rgb(214, 214, 214) !important;
  border: transparent !important;
  /* padding: 2rem; */
}
.container .is-left, .is-right {
  border-radius: 999999999px !important;
}

</style>