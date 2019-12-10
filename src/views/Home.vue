<template>
  <div
    class="bg-auto bg-center h-screen flex justify-center -mt-6 bg-black"
    :style="{ backgroundImage: `url(${backgroundImg})` }"
  >
    <h1 class="text-yellow-400 mt-10 text-6xl">Vue Wars</h1>
  </div>
</template>

<script>
import backgroundImg from "../assets/starwarswp.jpg";

export default {
  data() {
    return {
      backgroundImg
    };
  }
};
</script>
