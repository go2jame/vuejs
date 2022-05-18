<template>
  <h1>{{message}}</h1>
</template>

<script>
export default {
    name:"FormComponent",
    data(){
        return {
            message:"แบบฟอร์มบันทึกข้อมูลพนักงาน"
        }
    }
}
</script>

<style scoped>
    h1{
        color:green;
        font-weight: bold;
    }
</style>