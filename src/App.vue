<template>
  <header>
    ้<h1>ระบบจัดการข้อมูลพนักงาน</h1>    
  </header>
  <section class="employee-content">
    <ListData />
  </section>
  
</template>

<script>
// import FormComponent from './components/FormComponent.vue';
import ListData from './components/ListData.vue';
// import MyComponent from "./components/MyComponent.vue";

export default {
  name: "App",
  components: {
    // MyComponent,
    ListData,
    // FormComponent,
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}

*{
  box-sizing: border-box;
}
header{
  box-shadow: 0 2px 8px #2c3e50;
  border-radius: 6px;
  padding: 1rem;
  background:purple;
  color:white;
  text-align: center;
  margin: 3rem;
}
.employee-content{
  box-shadow: 0 2px 8px #2c3e50;
  border-radius: 6px;
  padding: 1rem;
  text-align: center;
  margin: 3rem;
}
</style>
