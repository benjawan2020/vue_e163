<template>
  <v-form
    ref="form"
    v-model="valid"
    lazy-validation
  >
  
    <v-text-field
      v-model="code"
      :counter="10"
      label="รหัสนักเรียน"
    ></v-text-field>

     <v-text-field
      v-model="pre_name"
      :counter="10"
      label="คำนำหน้า"
    ></v-text-field>

    <v-text-field
      v-model="first_name"
      :counter="10"
      label="ชื่อ"
    ></v-text-field>

    <v-text-field
      v-model="last_name"
      label="นามสกุล"
    ></v-text-field>

    <v-text-field
      v-model="is_active"
      :counter="10"
      label="สถานะ"

    ></v-text-field>

    <v-btn color="pink" class="mr-4" @click="saveStd">Save</v-btn>
  </v-form>
</template>
<script>
export default {
  data: () => ({
      code: '',
      pre_name: '',
      first_name:'',
      last_name:'',
      is_active: '',
  }),
  async created() {
    console.log("code_edit=", this.$route.query.code);
    let code = this.$route.query.code;
    let res = await fetch("http://localhost:7001/editstd?code=" + code);
    let data = await res.json();
    console.log('api_send', data.row[0].code)
    this.code = data.row[0].code
    this.pre_name = data.row[0].pre_name
    this.first_name = data.row[0].first_name
    this.last_name = data.row[0].last_name
    this.is_active = data.row[0].is_active
  },
  methods: {
    async submit(){
      let res = await fetch(
        "http://localhost:7001/insert?code=" +this.code + "&pre_name=" + this.pre_name + "&first_name=" + this.first_name + "&last_name=" +
          this.last_name + "&is_active=" + this.is_active
      )
    },
    async saveStd() {
      console.log('saveStd')
      let student = {
        code: this.code,
        pre_name: this.pre_name,
        first_name: this.first_name,
        last_name: this.last_name,
        is_active: this.is_active,
      }
      let res = await this.$http.post('http://localhost:7001/addstd2', student)
      console.log('row=', res.data.row)
    },
  },
};
</script>