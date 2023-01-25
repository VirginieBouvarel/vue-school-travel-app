<template>
  <div class="card">
    <img :src="`/images/${experience.image}`" :alt="experience.name" width="250" height="150"/>
    <span class="card-text">{{  experience.name  }}</span>
  </div>
</template>

<script>
  export default {
    props: {
      experience: { type: Object, required: true }
    }
  }
</script>

<style lang="scss" scoped>

</style>