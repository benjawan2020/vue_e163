<template>
  <v-form
    ref="form"
    v-model="valid"
    lazy-validation
  >
  
    <v-text-field
      v-model="std_id"
      :counter="10"
      label="student_id"
    ></v-text-field>

    <v-text-field
      v-model="name"
      :counter="10"
      label="Name"
    ></v-text-field>

    <v-text-field
      v-model="lastname"
      label="Lastname"
    ></v-text-field>

    <v-text-field
      v-model="gpa"
      :counter="10"
      label="GPA"

    ></v-text-field>

    <v-btn
      color="error"
      class="mr-4"
    >
      Reset Form
    </v-btn>
  </v-form>
</template>
<script>
  export default {
    data: () => ({
      user:'4921010026',
      std_id:'',
      name:'',
      lastname:'',
      gpa:'',
      name: '',
    }),

    methods: {
        async init_load(){
        console.log("welcome")
        let res = await fetch('http://localhost:7001/list?user='+this.user)
        let data = await res.json();
        console.log('data=',data.rows[0].GPA);
        this.gpa=data.rows[0].GPA;
        this.name=data.rows[0].name;
        this.lastname=data.rows[0].lastname;
        this.std_id=data.rows[0].student_id;

        }
    },
    created (){
       this.init_load();
    },
  }
</script>