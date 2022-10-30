<template>
  <div class="page">
    <TheSection1 />
    <TheSection2 />
  </div>
</template>

<script>
import TheSection1 from '@/components/TheSection1.vue';
import TheSection2 from '@/components/TheSection2.vue';

export default {
  name: 'HomeView',
  components: {
    TheSection1,
    TheSection2,
  },
};
</script>
