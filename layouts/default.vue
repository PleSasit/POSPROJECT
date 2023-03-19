<template>
    <div>
      <Nav />
      <div class="container">
          <Nuxt></Nuxt>
      </div>
    </div>
   
    
  </template>
  
  <script>
  export default {
    name: 'IndexPage',
    data() {
      return {
        data: [],
      };
    },
    mounted() {
      this.getData();
    },
    methods: {
      async getData() {
        const { data } = await this.$axios.get();
        this.data = data;
      },
    },
  }
  </script>
  