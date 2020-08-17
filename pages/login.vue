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
        <h1>Login</h1>
        <br>
        {{gpa}}
      </center>


     <v-card-text>
       <v-form>
         <v-text-field  v-model="user" prepend-icon="mdi-account-circle" label="Username" />
         <v-text-field 
          :type="showPassword ? 'text' : 'password'" 
            label="Password"
            v-model="password"
            prepend-icon="mdi-lock"
            :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
            @click:append="showPassword = !showPassword"/>
       </v-form>
     </v-card-text>

     <v-card-actions>
        <nuxt-link to="/register">
            <v-btn color="success">REGISTER</v-btn> </nuxt-link>
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
      let res = await fetch('http://localhost:7001/list?user='+this.user)
      let data = await res.json()
      console.log('data=',data.rows[0].GPA)
      this.gpa= data.rows[0].GPA
    },
  },
}
</script>