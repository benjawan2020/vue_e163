<template>
<div style="color: #fff;" class="bg1">
    <v-container>
        <h1>Card List</h1>
      <ul>
          <li v-for="std in student" :key="std.ref_code">
              <span>{{std.ref_code}}</span>
              <span>{{std.card_code}}</span>
              <span>{{std.ref_type}}</span>
              <span>{{std.is_active}}</span>
              <v-btn rounded color="warning" @click="edit(std.ref_code)" dark>แก้ไข</v-btn>
              <v-btn rounded color="error" @click="Del(std.ref_code)" dark>ลบ</v-btn><br><br>
          </li>
      </ul>
      <center>
          <v-btn @click="liscard" color="teal">list </v-btn>
      </center>
    </v-container>
</div>
</template>
<script>
  export default {
      layout:"card",
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
            this.$router.push('edit_card1?ref_code=' + ref_code)
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

