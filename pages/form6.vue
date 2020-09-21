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
        <h1>ข้อ6</h1>
        <br>
      </center>


     <v-card-text>
       <v-form>
         <v-text-field  v-model="school_id" prepend-icon="mdi-account-circle" label="รหัสสถานศึกษา" />
         <v-text-field  v-model="gpa" prepend-icon="mdi-account-circle" label="GPA" />
        
       </v-form>
     </v-card-text>

     <v-card-actions>
             <v-spacer></v-spacer>
            <v-btn color="primary" @click="form6">LOGIN</v-btn>
     </v-card-actions>

   </v-card>
</template>
<script>
export default {
  name: "App",
  data() {
    return {
      showPassword: false,
      school_id: "",
      gpa: "",
    };
  },
  methods: {
    async form6() {
      console.log("Form6");
      let res = await fetch(
        "http://localhost:7001/form6?school_id=" +this.school_id +"&gpa=" +this.gpa);
      let data = await res.json();
    },
  },
};
</script>