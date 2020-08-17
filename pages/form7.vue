<template>
    <v-card
    color="blue accent-4"
    dark
    height="400"
    width="500"
    class="teal lighten-1"
  >
      <center>
        <v-icon size="120">perm_identity</v-icon><br>
        <font Face="TH SarabunPSK" style="font-size: 15px;">แสดงนักศึกษาทุกวิทยาลัยที่มีผลการเรียน GPA 4.00</font>
      </center>


     <v-card-text>
       <v-form>
         <v-text-field  v-model="id" prepend-icon="mdi-account-circle" label="กรุณากรอกรหัสนักศึกษา" />
       </v-form>
     </v-card-text>

     <v-card-actions>
             <v-spacer></v-spacer>
             <v-btn rounded color="success" dark  @click="form7">ค้นหา</v-btn>
     </v-card-actions>

   </v-card>
</template>
<script>
export default {
  name: 'App',
  data () {
    return {
      showPassword: false,
      id: '',
    }
  },
  methods:{
   async form7(){
      console.log("form7")
      console.log("id:", this.id)
      let res = await fetch('http://localhost:7001/form7?id='+this.id)
      let data = await res.json()
    }
  },
}
</script>