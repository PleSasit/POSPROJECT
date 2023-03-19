<template>
  <div class= "text-center">
    <h2>Menu</h2> <br>
    <div class="btn">    
      <b-button href = "/addpage">เพิ่มรายการอาหาร</b-button>
    </div>
    <div class="text-center">
      <div class="row">
        <div class="col-4 "  v-for="i in data" :key="i.id">
          <Pos :price = "i.price" :name = "i.name" :img = "i.img ?? 'https://t4.ftcdn.net/jpg/04/72/65/73/360_F_472657366_6kV9ztFQ3OkIuBCkjjL8qPmqnuagktXU.jpg'" :des = "i.des"/>
          <br>
        </div>
      </div>
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

<style scoped>
  h2 { color: #349f9f; 
  font-family: 'Rouge Script', 
  cursive; font-size: 80px; 
  font-weight: normal; 
  line-height: 48px; 
  margin: 30px 0px 0px 30px; 
  text-align: center; 
  text-shadow: 1px 1px 2px #082b34; }


</style>
