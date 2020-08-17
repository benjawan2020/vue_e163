<template>
    <v-card
    color="green accent-4"
    dark
    height="400"
    width="500"
    class="teal lighten-1"
  >
      <center>
        <v-icon size="120">store_mall_directory</v-icon><br>
        <font Face="TH SarabunPSK" style="font-size: 20px;">นักเรียนคนนี้อยู่วิทยาลัยอะไร ต้องใช้2table</font>
      </center>


     <v-card-text>
       <v-form>
         <v-text-field  v-model="id" prepend-icon="mdi-account-circle" label="กรุณากรอกรหัสนักศึกษา" />
       </v-form>
     </v-card-text>

     <v-card-actions>
             <v-spacer></v-spacer>
            <v-btn color="primary" @click="form3">ค้นหา</v-btn>
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
   async form3(){
      console.log("form3")
      console.log("id:", this.id)
      //this.$router.push('/register')
      let res = await fetch('http://localhost:7001/form3?id='+this.id)
      let data = await res.json()
    }
  }
}
</script>