<template>
    <v-card
    color="green accent-3"
    dark
    height="400"
    width="500"
    class="teal lighten-1"
  >
      <center>
        <v-icon size="120">domain</v-icon><br>
         <font Face="TH SarabunPSK" style="font-size: 20px;">แสดงชื่อเว็บของวิทยาลัยที่มีใน Databases</font>
      </center>


     <v-card-text>
       <v-form>
         <v-text-field  v-model="id" prepend-icon="mdi-account-circle" label="กรุณากรอกรหัสวิทยาลัย" />
       </v-form>
     </v-card-text>

     <v-card-actions>
             <v-spacer></v-spacer>
            <v-btn rounded color="error" dark  @click="form2">ค้นหา</v-btn>
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
   async form2(){
      console.log("form2")
      console.log("user:", this.id)
      //this.$router.push('/register')
      let res = await fetch('http://localhost:7001/form2?id='+this.id)
      let data = await res.json()
    }
  },
}
</script>