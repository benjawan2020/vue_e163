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
        <h1>ข้อ3</h1>
        <br>
      </center>


     <v-card-text>
       <v-form>
         <v-text-field  v-model="student_id" prepend-icon="mdi-account-circle" label="รหัสนักศึกษา" />
         <v-text-field  v-model="school" prepend-icon="mdi-account-circle" label="ชื่อสถานศึกษา" />
        
       </v-form>
     </v-card-text>

     <v-card-actions>
             <v-spacer></v-spacer>
            <v-btn color="primary" @click="doSave">LOGIN</v-btn>
     </v-card-actions>

   </v-card>
</template>
<script>
export default {
  name: 'App',
  data () {
    return {
      showPassword: false,
      student_id:'',
      school:'',
      user: '',
      password: '',
      GPA:''
    }
  },
  methods:{
   async doSave(){
      console.log("do save")
      console.log("user:", this.user)
      console.log("password:", this.password)
      //this.$router.push('/register')
      let res = await fetch('http://localhost:7001/form3?student_id='+this.student_id)
      let data = await res.json()
      console.log('data=',data.rows[0].school_name)
      this.school= data.rows[0].school_name
    },
  },
}
</script>