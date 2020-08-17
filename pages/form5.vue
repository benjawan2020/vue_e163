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
        <font Face="TH SarabunPSK" style="font-size: 15px;">แสดงนักศึกษาทุกวิทยาลัยที่มีผลการเรียน GPA น้อยกว่า 3.50</font>
      </center>


     <v-card-text>
       <v-form>
         <v-text-field  v-model="id" prepend-icon="mdi-account-circle" label="กรุณากรอกรหัสนักศึกษา" />
       </v-form>
     </v-card-text>

     <v-card-actions>
             <v-spacer></v-spacer>
            <v-btn rounded color="success" dark  @click="form5">ค้นหา</v-btn>
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
   async form5(){
      console.log("form5")
      console.log("user:", this.id)
      //this.$router.push('/register')
      let res = await fetch('http://localhost:7001/form5?id='+this.id)
      let data = await res.json()
    }
  },
}
</script>