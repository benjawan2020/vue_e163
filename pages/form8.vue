<template>
    <v-card
    color="blue darken-4"
    dark
    height="450"
    width="500"
    class="mx-auto"
  >
      <center>
        <v-icon size="120">person</v-icon>
        <h1>ข้อ8</h1>
        <h2>ที่ตั้งจังหวัด {{province}}</h2>
        <br>
      </center>


     <v-card-text>
       <v-form>
         <v-text-field  v-model="province_id" prepend-icon="mdi-account-circle" label="รหัสจังหวัด" />
       </v-form>
     </v-card-text>

     <v-card-actions>
             <v-spacer></v-spacer>
            <v-btn color="primary" @click="doSearch">LOGIN</v-btn>
     </v-card-actions>

   </v-card>
</template>
<script>
export default {
  name: 'App',
  data() {
    return {
      province: '',
      province_id: '',
      school: '',
      user: '',
      password: '',
      gpa: '',
    }
  },
  methods: {
    async doSearch() {
      console.log('do search  provice')
      let res = await fetch('http://localhost:7001/province?province_id=' + this.province_id)
      let data = await res.json()
      console.log(data.rows[0].province_name)
      this.province = data.rows[0].province_name

    },
  },
}
</script>