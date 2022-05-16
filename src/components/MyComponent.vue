<template>
  <div id="hello">
    <h1>TEST</h1>
    <div>{{ getFullName }}</div>
    <form @submit.prevent="submitForm">
      <label for="fname">Name : </label>
      <input
        type="text"
        id="fname"
        name="fname"
        v-model="fname"
        ref="nameInput"
      />
      <button>Submit</button>
    </form>
    <div>{{ fname }}</div>
    <div>{{ inputName }}</div>
    <p v-if="hobby.length === 0">ไม่มีงานอดิเรก</p>
    <div v-else>
      <ul>
        <li v-for="(item, index) in hobby" v-bind:key="index">{{ item }}</li>
      </ul>
    </div>
    <button @click="toggleVisible">
      {{ isVisible ? "ซ่อน" : "แสดง" }}รายละเอียด
    </button>
    <article v-show="isVisible">
      <ul>
        <li v-for="(item, index) in general" v-bind:key="index">
          {{ index }} - {{ item }}
        </li>
      </ul>
    </article>

    <h2>Method1 : {{ getRamdombyMethod() }}</h2>
    <h2>Method2 : {{ getRamdombyMethod() }}</h2>
    <br />
    <h2>Method1 : {{ getRamdombyComputed }}</h2>
    <h2>Method2 : {{ getRamdombyComputed }}</h2>
    <h2>Method3 : {{ getRamdombyComputed }}</h2>
    <div>เงินเดือน {{ salary }} บาท</div>
    <div>รายได้ต่อปี {{ getIncome }} บาท</div>
    <h1>ตำแหน่ง {{ getDepartment }}</h1>
    <button @click="addSalary(5000)">เพิ่มเงินเดือน</button>
  </div>
</template>

<script>
export default {
  name: "MyComponent",
  data() {
    return {
      firstName: "Thananan",
      lastName: "Chaisiriphutthichok",
      fname: "",
      inputName: "",
      hobby: ["อ่านหังสือ", "ออกกำลังกาย"],
      general: { gender: "ชาย", weight: 70, height: 170, status: false },
      isVisible: false,
      salary: 20000,
    };
  },
  methods: {
    submitForm() {
      // console.log(this.$refs.nameInput);
      this.inputName = this.$refs.nameInput.value;
    },
    toggleVisible() {
      this.isVisible = !this.isVisible;
      console.log(this.isVisible);
    },
    getRamdombyMethod() {
      return Math.random();
    },
    addSalary(value) {
      this.salary += value;
    },
  },
  computed: {
    getFullName() {
      return this.firstName + " " + this.lastName;
    },
    getRamdombyComputed() {
      return Math.random();
    },
    getIncome() {
      return this.salary * 12;
    },
    getDepartment() {
      return this.salary >= 35000 ? "Project Manager" : "Programmer";
    },
  },
  watch:{
    salary(value){
      if (value>50000) {
        alert("เงินเดือนไม่ควรเกิน 50,000 บาท");
        setTimeout(()=>{
          this.salary=50000
        },2000);
      }
    }
  }
};
</script>

<style scoped>
/* #hello {
  color:blue;
} */
a {
  color: #4a0148;
}
</style>