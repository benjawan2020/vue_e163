<template>
<div>
      <v-data-table
    :headers="headers"
    :items="student"
    :items-per-page="5"
    class="elevation-1"
  ></v-data-table>
  <v-btn @click="listStd">Click</v-btn>
</div>
</template>
<script>
  export default {
    data () {
      return {
        headers: [
          {
            text: 'รหัสนักศึกษา',
            align: 'start',
            sortable: false,
            value: 'code',
          },
          { text: 'ชื่อ', value: 'first_name' },
          { text: 'สกุล', value: 'last_name' },
          { text: 'สถานะ', value: 'is_active' },

        ],
        student: [
        ],
      }
    },
    methods:{
    async listStd(){
           console.log("liststd")
           let res =  await fetch("http://localhost:7001/liststd2")
           let data = await res.json()
           console.log('data=',data)
           this.student = data.rows
       }
    }
  }
</script>
