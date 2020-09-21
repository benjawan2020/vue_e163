<template>
  <v-data-table
    :headers="headers"
    :items="desserts"
    :items-per-page="5"
    class="elevation-1"
  ></v-data-table>
</template>
<script>
  export default {
    data () {
      return {
        headers: [
          {
            text: 'code',
            align: 'start',
            sortable: false,
            value: 'code',
          },
          { text: 'ชื่อ - สกุล', value: 'first_name' },
          { text: 'สถานะ', value: 'is_active' },
        ],
        desserts: [
          {
            std_id: '1111111',
            fname: 'นางสาวเบญจวรรณ สิงหอำพล',
            status: 'ใช้งาน',
          },
          {
            std_id: '2222222',
            fname: 'นางสาวพรกมล อยู่ภักดี',
            status: 'ระงับ',
          },
        ],
      }
    },
created(){
    this.listStd()
},
    methods:{
        async listStd(){
            let res = await fetch("http://localhost:7001/listStd")
            let data = await res.json()
            console.log('datas=', data.rows)
            this.desserts = data.rows[0]
        },
    },
  }
</script>