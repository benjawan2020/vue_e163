<template>
    <div style="color: #fff;" class="bg1">
        <v-container>
            <v-form
    ref="form"
    v-model="valid"
    lazy-validation
  >
  
    <v-text-field
      v-model="card_code"
      :counter="10"
      label="รหัส"
    ></v-text-field>

     <v-text-field
      v-model="ref_type"
      :counter="10"
      label="สถานะผุ้ใช้"
    ></v-text-field>

    <v-text-field
      v-model="ref_code"
      :counter="10"
      label="รหัสนักศึกษา"
    ></v-text-field>

    <v-text-field
      v-model="is_active"
      :counter="10"
      label="สถานะ"

    ></v-text-field>
        <center>
             <v-btn color="#0018ff" class="mr-4" @click="saveCard">Save</v-btn>
        </center>
  </v-form>
        </v-container>
    </div>
</template>
<script>
export default {
    layout:"card",
  data: () => ({
      card_code: '',
      ref_type: '',
      ref_code:'',
      is_active: '',
  }),
  async created() {
    console.log("code_edit=", this.$route.query.ref_code);
    let ref_code = this.$route.query.ref_code;
    let res = await fetch("http://localhost:7001/editcard?ref_code=" + ref_code);
    let data = await res.json();
    console.log('api_send', data.row[0].ref_code)
    this.card_code = data.row[0].card_code
    this.ref_type = data.row[0].ref_type
    this.ref_code = data.row[0].ref_code
    this.is_active = data.row[0].is_active
  },
  methods: {
    async submit(){
      let res = await fetch(
        "http://localhost:7001/insert?code=" +this.code + "&pre_name=" + this.pre_name + "&first_name=" + this.first_name + "&last_name=" +
          this.last_name + "&is_active=" + this.is_active
      )
    },
    async saveCard() {
      console.log('saveCard')
      let card = {
        card_code: this.card_code,
        ref_type: this.ref_type,
        ref_code: this.ref_code,
        is_active: this.is_active,
      }
       let res = await fetch('http://localhost:7001/addCard', {
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