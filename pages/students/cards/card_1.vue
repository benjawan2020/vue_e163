<template>
<div style="color: #fff;">
      <h1>Student List</h1>
      <ul>
          <li v-for="std in student" :key="std.ref_code">
              <span>{{std.ref_code}}</span>
              <span>{{std.card_code}}</span>
              <span>{{std.ref_type}}</span>
              <span>{{std.is_active}}</span>
              <v-btn @click="edit(std.ref_code)">EDIT </v-btn>
              <v-btn @click="Del(std.ref_code)">DEL</v-btn>
          </li>
      </ul>
      <v-btn @click="liscard">list </v-btn>
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
            value: 'ref_code',
          },
          { text: 'รหัสการ์ด', value: 'card_code' },
          { text: 'สถานะ', value: 'ref_type' },
          { text: 'สถานะการใช้งาน', value: 'is_active' },

        ],
        student: [
        ],
      }
    },
    created(){
        this.liscard()
    },
    methods: {
    async  liscard(){
        console.log('liscard')
      let res  = await fetch('http://localhost:7001/listCard')
      let data = await  res.json()
      console.log('data=',data)
      this.student = data.rows
      },
        edit(ref_code){
            console.log('ref_code=',ref_code)
            this.$router.push('edit_card?ref_code=' + ref_code)
         },
        async Del(ref_code){
      console.log('ref_code=' , ref_code)
      let res = await this.$http.post('http://localhost:7001/delcard?ref_code=' + ref_code)
      console.log(res.data.status)
      if(res.data.status= 'ok'){
      }
    }
    },
  }
</script>
