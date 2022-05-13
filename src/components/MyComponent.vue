<template>
  <div id="hello">
    <h1>TEST</h1>
    <div>{{ getFullName() }}</div>
  </div>
</template>

<script>
export default {
  name: "MyComponent",
  data() {
    return {
      firstName: "Thananan",
      lastName: "Chaisiriphutthichok",
    };
  },
  methods: {
      getFullName() {
          return this.firstName + " " + this.lastName;
      }
  }
};
</script>

<style scoped>
#hello{
    color:red;
}
a {
  color: #4a0148;
}
</style>