<template>
  <div
    class="relative bg-white dark:bg-gray-800 transform transition duration-500"
  >
    <div class="flex items-center justify-center flex-col">
      <div class="pt-28 flex-1 flex items-center justify-center flex-col px-4 sm:px-6 md:px-8 lg:px-16 xl:px-36 2xl:px-488">
        <div class="text-6xl font-bold dark:text-white">
          <p class="join-team-text mb-3">
            <span style="animation: fadeInBottom 0.5s ease-in-out 0.6s both"
              >Join<i class="hidden md:inline">&nbsp;</i></span
            >
            <span style="animation: fadeInBottom 0.5s ease-in-out 0.5s both"
              >Our<i class="hidden md:inline">&nbsp;</i></span
            >
            <span style="animation: fadeInTop 0.5s ease-in-out 0.6s both"
              >Team</span
            >
          </p>
          <p class="join-team-text mb-3">
            <span style="animation: fadeInBottom 0.5s ease-in-out 0.6s both"
              >Let's<i class="hidden md:inline">&nbsp;</i>
            </span>
            <span style="animation: fadeInTop 0.5s ease-in-out 0.5s both"
              >build<i class="hidden md:inline">&nbsp;</i>
            </span>
            <span style="animation: fadeInBottom 0.5s ease-in-out 0.6s both"
              >a<i class="hidden md:inline">&nbsp;</i>
            </span>
            <span style="animation: fadeInTop 0.5s ease-in-out 0.5s both"
              >"Noah's<i class="hidden md:inline">&nbsp;</i>
            </span>
            <span style="animation: fadeInBottom 0.5s ease-in-out 0.6s both"
              >Ark"</span
            >
          </p>
          <p class="join-team-text">
            <span style="animation: fadeInBottom 0.5s ease-in-out 0.8s both"
              >Together.</span
            >
          </p>
        </div>
        <div class="text-gray-500 dark:text-gray-400 mt-10">
          <div
            class="mb-4 text-lg md:w-[768px] text-center"
            style="
              word-wrap: break-word;
              animation: fadeInBottom 0.5s ease-in-out 1s both;
            "
          >
            Our diverse team unites under a shared passion for shaping the
            digital future. With expertise spanning mathematics, machine
            learning, physics, and business, we synergize our varied backgrounds
            to evaluate and propel research ideas. Together, we forecast their
            potential and feasibility, driving forward our mission with
            precision and innovation.
          </div>
        </div>
      </div>
      <div class="my-28 learn-more-button">
        <LearnMoreButton />
      </div>

      <div class="mt-10 ">
        <TeamCanvas class="team-canvas" />
      </div>
    </div>

    <div
      class="relative z-10 flex flex-col items-center justify-center h-64 rounded-md p-6 bg-white dark:bg-gray-800"
    >
      <h2 class="text-2xl font-semibold text-gray-800 dark:text-white mb-4">
        暂时没有招募计划
      </h2>
      <p class="dark:text-gray-300">团队暂时并未扩招</p>
    </div>
  </div>
</template>

<script setup lang="ts">
import TeamCanvas from "@/components/TeamCanvas.vue";
import { gsap } from "gsap";
import { onMounted } from "vue";
import LearnMoreButton from "@/views/team/LearnMoreButton.vue";

onMounted(() => {
  gsap.from(".team-canvas", {
    yPercent: 300,
    duration: 1,
    delay: 0.4,
  });
  gsap.from(".learn-more-button", {
    yPercent: 300,
    opacity: 0,
    duration: 1,
    delay: 0.6,
  });

});
</script>
<style scoped>
.join-team-text {
  span {
    display: inline-block;
  }
}
</style>
