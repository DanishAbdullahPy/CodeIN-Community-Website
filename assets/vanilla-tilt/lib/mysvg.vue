<template>
  <div class="svg-container">
    <svg
      width="100%"
      height="100%"
      id="svg"
      viewBox="0 0 1440 590"
      xmlns="http://www.w3.org/2000/svg"
      class="transition duration-300 ease-in-out delay-150"
    >
      <defs>
        <linearGradient id="gradient" x1="0%" y1="50%" x2="100%" y2="50%">
          <stop offset="5%" stop-color="#d80032"></stop>
          <stop offset="95%" stop-color="#ff6900"></stop>
        </linearGradient>
      </defs>
      <path
        :class="'transition-all duration-300 ease-in-out delay-150 path-' + pathNumber"
        :d="getPathData(pathNumber)"
        stroke="none"
        stroke-width="0"
        fill="url(#gradient)"
        fill-opacity="0.53"
      ></path>
    </svg>
  </div>
</template>

<script>
export default {
  data() {
    return {
      pathNumber: 0,
    };
  },
  methods: {
    getPathData(pathNumber) {
      switch (pathNumber) {
        case 0:
          return "M 0,600 C 0,600 0,200 0,200 C 132.96428571428572,151.92857142857144 265.92857142857144,103.85714285714286 383,132 C 500.07142857142856,160.14285714285714 601.2500000000001,264.5 723,272 C 844.7499999999999,279.5 987.0714285714287,190.14285714285714 1110,162 C 1232.9285714285713,133.85714285714286 1336.4642857142858,166.92857142857144 1440,200 C 1440,200 1440,600 1440,600 Z";
        case 1:
          return "M 0,600 C 0,600 0,400 0,400 C 92.53571428571428,404.1071428571429 185.07142857142856,408.2142857142857 308,410 C 430.92857142857144,411.7857142857143 584.25,411.25 729,420 C 873.75,428.75 1009.9285714285713,446.7857142857143 1127,445 C 1244.0714285714287,443.2142857142857 1342.0357142857142,421.6071428571429 1440,400 C 1440,400 1440,600 1440,600 Z";
        // Add more cases as needed for other paths
        default:
          return "";
      }
    },
  },
  mounted() {
    // Set up animation for the paths
    setInterval(() => {
      this.pathNumber = (this.pathNumber + 1) % 2; // Change 2 to the total number of paths
    }, 4000); // Set the duration of each path's animation
  },
};
</script>

<style scoped>
.svg-container {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
