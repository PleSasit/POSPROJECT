<template>
    <div>
        <b-card
        style="object-fit: cover"
        img-height="250"
        :title="name"
        :img-src="img"
        img-alt="Image"
        img-top
        >
        <b-card-text>
            {{ des }} <br />
            ราคา {{ price }} บาท <br>
            <div class="btn">
                <b-button>ลบรายการ</b-button>
                <b-button v-b-modal="'my-modal'">แก้ไข</b-button>
            </div>

  <!-- The modal -->
  <b-modal id="my-modal">Hello From My Modal!</b-modal>
        </b-card-text>

        <template #footer>
            <strong class="text-muted"></strong>
            <b-button block variant="primary">สั่งเลย</b-button>
        </template>
        </b-card>
    </div>
</template>

<script>
export default {
  props: {
    price: {
      type: Number,
      default: 0,
    },
    name: {
      type: String,
      default: "",
    },
    img: {
      type: String,
      default: "",
    },
    des: {
      type: String,
      default: "",
    },
  },
};

</script>
<style scoped>
/* .btn {
    background-color: rgb(44, 139, 241);
} */
</style>
