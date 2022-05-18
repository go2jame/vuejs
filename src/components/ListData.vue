<template>
  <div id="ListData">
    <!-- <h1>{{ message }}</h1> -->
    <ul>
      <Person
        v-for="item in employees"
        :id="item.id"
        :key="item.id"
        :name="item.name"
        :salary="item.salary"
        :isVisible="item.isVisible"
        @show="toggleVisible"
      />
    </ul>
  </div>
</template>

<script>
import Person from "./Person.vue";
export default {
  name: "ListData",
  components: {
    Person,
  },
  data(){
    return{
      employees:[
        {id:1,name:"James" ,salary:10000, isVisible: false},
        {id:2,name:"Thananan",salary:10000, isVisible: false},
        {id:3,name:"Somchai",salary:25000, isVisible: false},
        {id:4,name: "1234",salary:23000, isVisible: false},
      ]
    }
  },
  methods:{
      toggleVisible(id){
          this.employees = this.employees.map((item)=>{
              if(item.id === id){
                  return {...item,isVisible:!item.isVisible}
              }
              return item;
          })
      }
  }
};
</script>

<style scoped>
ul{
    list-style: none;
}
</style>