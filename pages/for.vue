<template>
  <div style="color: #000;">
    <h1>Student List</h1>
        <v-data-table
    :headers="headers"
    :items="student"
    :items-per-page="5"
    class="elevation-1"
  ></v-data-table>
  </div>
</template>

<script>
export default {
  data() {
    return {
        headers: [
          {
            text: 'รหัสนักศึกษา',
            align: 'start',
            sortable: false,
            value: 'student_id',
          },
          { text: 'ชื่อ', value: 'name' },
          { text: 'นามสกุล', value: 'lastname' },
          { text: 'เกรดเฉลี่ย', value: 'GPA' },
        ],
      student: [],
    }
  },
   methods: {
    async listStudent() {
      console.log("list std");
      let res = await fetch("http://localhost:7001/listStd")
      let data = await res.json()
      console.log('data',data.rows[0])
      this.student = data.rows[0]
    },
   },
    created(){
      this.listStudent()
},
}
</script>