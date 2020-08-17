<template>
    <v-card
    color="blue darken-4"
    dark
    height="400"
    width="500"
    class="teal lighten-1"
  >
      <center>
        <v-icon size="120">account_balance</v-icon><br>
        <font Face="TH SarabunPSK" style="font-size: 15px;">วิทยาลัยนี้แสดงชื่อผู้หญิงทั้งหมดพร้อมแสดงชื่อวิทยาลัย</font>
      </center>


     <v-card-text>
       <v-form>
         <v-text-field  v-model="id" prepend-icon="mdi-account-circle" label="กรุณากรอกชื่อสถานศึกษา" />
       </v-form>
     </v-card-text>

     <v-card-actions>
             <v-spacer></v-spacer>
            <v-btn rounded color="success" dark  @click="form4">ค้นหา</v-btn>
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
   async form4(){
      console.log("form4")
      console.log("user:", this.id)
      //this.$router.push('/register')
      let res = await fetch('http://localhost:7001/form4?id='+this.id)
      let data = await res.json()
    }
  },
}
</script>