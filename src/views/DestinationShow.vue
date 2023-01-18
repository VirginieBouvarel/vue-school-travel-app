<template>
  <section v-if="destination" class="destination">
    <h1>{{ destination.name }}</h1>
    <div class="destination-details">
      <img :src="`/images/${destination.image}`" :alt="destination.name" width="600" height="300">
      <p>{{ destination.description }}</p>
    </div>
  </section>
</template>

<script>
  export default {
    data() {
      return {
        destination: null,
      };
    },
    methods: {
      async initData() {
        const response = fetch(`https://travel-dummy-api.netlify.app/${this.$route.params.slug}`);
        this.destination = await response.json();
      },
    },
    async created() {
      this.initData();
    }
  }
</script>

<style lang="scss" scoped>

</style>