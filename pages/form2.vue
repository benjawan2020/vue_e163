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
        <h1>ข้อ2</h1>
        <br>
      </center>


     <v-card-text>
       <v-form>
         <v-text-field  v-model="school_id" prepend-icon="mdi-account-circle" label="รหัสสถานศึกษา" />
         <v-text-field  v-model="web_url" prepend-icon="mdi-account-circle" label="url" />
        
       </v-form>
     </v-card-text>

     <v-card-actions>
             <v-spacer></v-spacer>
            <v-btn color="primary" @click="form2">LOGIN</v-btn>
     </v-card-actions>

   </v-card>
</template>
<script>
export default {
  data() {
    return {
      school_id: "",
      web_url: "",
    };
  },
  methods: {
    async form2() {
      console.log("Success Form2");
      console.log("school_id:", this.school_id);
      //this.$router.push('/register')
      let res = await fetch(
        "http://localhost:7001/form2?school_id=" + this.school_id
      );
      let data = await res.json();
      this.school_id = data.rows[0].school_id;
      this.web_url = data.rows[0].web_url;
    },
  },
};
</script>