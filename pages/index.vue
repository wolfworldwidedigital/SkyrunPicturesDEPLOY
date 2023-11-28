<template>
  <div>
    <IntroVideo v-if="showIntro" @videoEnded="closeIntro" />
    <HomeVideo v-else />
  </div>
</template>

<script setup>
import IntroVideo from '~/components/Intros/IntroVideo.vue';
import HomeVideo from '~/components/Intros/HomeVideo.vue';
import { ref, onMounted } from 'vue';

const showIntro = ref(true);

onMounted(() => {
  setTimeout(() => {
    showIntro.value = false;
  }, 20000); // 30 seconds
});

const closeIntro = () => {
  showIntro.value = false;
};

</script>
