<template>
  <div class="about">
    <index/>
    <!-- <index2/> -->
  </div>
</template>
<script>
import index from '@/components/wishcard/index.vue'
// import index2 from '@/components/wishcard/indexlocal.vue'
// @ is an alias to /src
export default {
  name: 'About',
  components: {
    index,
    // index2

  },
}
</script>