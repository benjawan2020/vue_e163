<template>
  <v-form
    ref="form"
    v-model="valid"
    lazy-validation
  >
  
    <v-text-field
      v-model="ref_code"
      :counter="10"
      label="รหัสนักเรียน"
    ></v-text-field>

     <v-text-field
      v-model="card_code"
      :counter="10"
      label="รหัสบัตร"
    ></v-text-field>

    <v-text-field
      v-model="ref_type"
      :counter="10"
      label="สถานะ"
    ></v-text-field>

    <v-text-field
      v-model="is_active"
      label="สถานะการใช้งาน"
    ></v-text-field>

    <v-btn color="pink" class="mr-4" @click="savecard">Save</v-btn>
  </v-form>
</template>
<script>
export default {
  data: () => ({
      ref_code: '',
      card_code: '',
      ref_type:'',
      is_active:'',
  }),
  async created() {
    console.log("ref_code=", this.$route.query.ref_code);
    let ref_code = this.$route.query.ref_code;
    let res = await fetch("http://localhost:7001/editcard?ref_code=" + ref_code);
    let data = await res.json();
    console.log('api_send', data.row[0].ref_code)
    this.ref_code = data.row[0].ref_code
    this.card_code = data.row[0].card_code
    this.ref_type = data.row[0].ref_type
    this.is_active = data.row[0].is_active
  },
  methods: {
    async submit(){
      let res = await fetch(
        "http://localhost:7001/insert?ref_code=" +this.ref_code + "&card_code=" + this.card_code + "&ref_type=" + this.last_name + "&is_active=" + this.is_active)
    },
    async savecard() {
      console.log('savecard')
      let card = {
        ref_code: this.ref_code,
        card_code: this.card_code,
        ref_type: this.ref_type,
        is_active: this.is_active,
      }
       let res = await fetch('http://localhost:7001/addcard', {
        method: 'post',
        headers: {
          'content-type': 'application/json',
        },
        body: JSON.stringify(card),
      })
      let data = await res.json()
      console.log('data=', data)
    },
  },
};
</script>