<template>
    <v-card>
      <center>
        <v-icon size="120">person</v-icon>
        <h1>ข้อ4</h1>
        <br>
      </center>


     <v-card-text>
       <v-form>
         <v-text-field  v-model="school_id" prepend-icon="mdi-account-circle" label="รหัสสถานศึกษา" />
       </v-form>
     </v-card-text>

     <v-card-actions>
             <v-spacer></v-spacer>
            <v-btn color="primary" @click="form4">LOGIN</v-btn>
     </v-card-actions>

     <v-data-table
    :headers="headers"
    :items="student"
    :items-per-page="5"
    class="elevation-1"
  ></v-data-table>

   </v-card>
</template>
<script>
export default {
  name: "App",
  data() {
    return {
       headers: [
          {
            text: 'รหัสนักศึกษา',
            align: 'start',
            sortable: false,
            value: 'student_id',
          },
          { text: 'ชื่อ', value: 'name' },
          { text: 'นามสกุล', value: 'lastname' },
          { text: 'เพศ', value: 'gender' },
        ],
      student: [],
      showPassword: false,
      school_id: "",
    };
  },
  methods: {
    async form4() {
      console.log("form4");
      let res = await fetch(
        "http://localhost:7001/form4?school_id=" +this.school_id);
      let data = await res.json();
      console.log('data',data.rows[0])
      this.student = data.rows[0]
    },
  },
};
</script>