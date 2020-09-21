<template>
<div style="color: #fff;">
      <h1>Student List</h1>
      <ul>
          <li v-for="std in student" :key="std.code">
              <span>{{std.code}}</span>
              <span>{{std.first_name}}</span>
              <span>{{std.last_name}}</span>
              <span>{{std.is_active}}</span>
              <v-btn @click="edit(std.code)">EDIT </v-btn>
          </li>
      </ul>
      <v-btn @click="listStd">list </v-btn>
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
    created(){
        this.listStd()
    },
    methods: {
    async  listStd(){
        console.log('liststd')
      let res  = await fetch('http://localhost:7001/liststd2')
      let data = await  res.json()
      console.log('data=',data)
      this.student = data.rows
      },
        edit(code){
            console.log('code=',code)
            this.$router.push('list_edit_std2?code=' + code)
         }
    },
  }
</script>
