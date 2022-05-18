<template>
  <li>
    <div>
        <div>
            <button @click="showDescription(id)">ดูรายละเอียด</button> &nbsp;
            <button>ลบ</button>
        </div>
    </div>
    <h1>{{ name }} </h1>
    <div  v-show="isVisible">เงินเดือน {{ salary }} บาท</div>
  </li>
</template>

<script>
export default {
  name: "Person",
  props: {
    id:{
        type: Number,
        required: true,
    },
    name: {
      type: String,
      required: true,
    },
    salary: {
      type: Number,
      default: 15000,
    },
    isVisible:{
        type:Boolean,
    }
  },

  data() {
    return {
      message: "ข้อมูลพนักงาน",
    };
  },

  methods:{
      showDescription(id){
          this.$emit("show",id);
      }
  }
};
</script>

<style scoped>
h1 {
  color: red;
}
</style>