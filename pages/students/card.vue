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
            text: 'id',
            align: 'start',
            sortable: false,
            value: 'id',
          },
          { text: 'รหัสการ์ด', value: 'card_code' },
          { text: 'สถานะ', value: 'ref_type' },
          { text: 'สถานะทั่วไป', value: 'ref_code' },
          { text: 'สถานะใช้งาน/ระงับ', value: 'is_active' },
          
        ],
        desserts: [],
      }
    },
created(){
    this.listStd()
},
    methods:{
        async listStd(){
            let res = await fetch("http://localhost:7001/listStd1")
            let data = await res.json()
            console.log('datas=', data.rows)
            this.desserts = data.rows[0]
        },
    },
  }
</script>