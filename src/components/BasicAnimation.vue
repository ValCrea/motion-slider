<script setup lang="ts">
import gsap from "gsap";
import { Motion, Presence } from "motion/vue";
import { ref, onMounted } from "vue";

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

const show = ref(true);
</script>

<template>
  <div>
    <button @click="show = !show">Animate</button>
    <p id="testx" class="brick-red">Move X</p>
    <p id="testy" class="brick-green">Move Y</p>
    <Presence>
      <Motion
        v-show="show"
        :initial="{ opacity: 0, scale: 0 }"
        :animate="{ opacity: 1, scale: 1 }"
        :exit="{ opacity: 0, scale: 0.6 }"
        class="brick-blue"
      >
        Opacity
      </Motion>
    </Presence>
  </div>
</template>

<style scoped>
.brick-red {
  width: 200px;
  height: 80px;
  color: darkred;
  background-color: lightcoral;
}

.brick-blue {
  width: 200px;
  height: 80px;
  color: darkblue;
  background-color: lightblue;
}

.brick-green {
  width: 200px;
  height: 80px;
  color: darkgreen;
  background-color: lightgreen;
}
</style>
