<script setup lang="ts">
import gsap from "gsap";
import { onMounted } from "vue";

onMounted(() => {
  gsap.fromTo(
    "#testx",
    {
      opacity: 0,
      x: "-100%",
    },
    {
      duration: 1.5,
      opacity: 1,
      x: 0,
      ease: "power3.inOut",
    }
  );

  gsap.fromTo(
    "#testy",
    {
      opacity: 0,
      y: "1000%",
    },
    {
      duration: 0.5,
      opacity: 1,
      y: 0,
      ease: "power3.inOut",
      delay: 1,
    }
  );
});
</script>

<template>
  <div>
    Animation:
    <p id="testx">Move X</p>
    <p id="testy">Move Y</p>
  </div>
</template>

<style scoped></style>
