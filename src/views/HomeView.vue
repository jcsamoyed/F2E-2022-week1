<template>
  <div class="page">
    <TheSection1 />
    <TheSection2 />
    <TheSection3 />
    <TheSection4 />
    <TheSection5 />
    <TheSection6 />
  </div>
</template>

<script>
import TheSection1 from '@/components/TheSection1.vue';
import TheSection2 from '@/components/TheSection2.vue';
import TheSection3 from '@/components/TheSection3.vue';
import TheSection4 from '@/components/TheSection4.vue';
import TheSection5 from '@/components/TheSection5.vue';
import TheSection6 from '@/components/TheSection6.vue';

export default {
  name: 'HomeView',
  components: {
    TheSection1,
    TheSection2,
    TheSection3,
    TheSection4,
    TheSection5,
    TheSection6,
  },
};
</script>
