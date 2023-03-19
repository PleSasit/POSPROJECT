<template>
    <form class="container">
         ชื่ออาหาร : <input type = "text" name = "name" v-model="name" />
         <br>
         ราคา: <input type = "text" name = "price" v-model="price" /><br>
         img link: <input type = "text" name = "img" v-model="img" /><br>
         Description : <br />
         <textarea rows = "5" cols = "50" name = "description" v-model="des">
            Enter description here...
         </textarea><br>
         <input type = "button" value="submit" @click="sendData">
    </form>

</template>

<script>
export default {
  name: 'AddPage',
  data() {
    return {
      name: '',price: '',img: '',des: ''
    };
  },
  mounted() {

  },
  methods: {
    async sendData() {
        this.$axios.post('/product', {
          name: this.name, 
          price: this.price,
          des: this.des,
          img:this.img
})
    },
  },
}
</script>
<style scoped>
.container{
    /* background-color:#64b2b0; */
    border-radius: 10px;
    padding: 30px;
    margin-top: 50px;
}
input[type=text] {
    margin: 8px 0;
    padding: 10px;
    box-sizing: border-box;
    border: 1px solid #ccc;
    outline: none;
    border-radius: 7px;
    width: 100%;
}
input[type=button] {
    border: none;
    border-radius: 7px;
    padding: 10px 40px;
    transition: 0.3s;
    color: #000000;
    background:#48aae0;
}
textarea {
    margin: 8px 0;
    padding: 10px;
    box-sizing: border-box;
    border: 1px solid #ccc;
    outline: none;
    border-radius: 7px;
    width: 100%;
}
</style>