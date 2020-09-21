<template>
  <form>
    <v-text-field
      v-model="card_code"
      label="รหัส_RFID"
    />
    <v-text-field
      v-model="ref_code"
      label="รหัสนักศึกษา"
    />
    <v-select
      prepend-icon="fas fa-th"
      :items="type"
      label="กลุ่ม"
      placeholder="กลุ่ม"
      v-model="ref_type"
    />
    <v-btn class="mr-4" @click="saveCard">
      SAVE
    </v-btn>
    <v-btn @click="clear">
      clear
    </v-btn>
  </form>
</template>

<script>
export default {
  data: () => ({
    card_code: '',
    ref_type: '',
    ref_code: '',
    register_date: '',
    is_active: '',
    created_at: '',
    update_at: '',
    type: ['teacher', 'student', 'guest'],
  }),
  methods: {
    async saveCard() {
      console.log('saveCard')
      let cardStd = {
        card_code: this.card_code,
        ref_type: this.ref_type,
        ref_code: this.ref_code,
        register_date: this.register_date,
        is_active: this.is_active,
      }
      let res = await this.$http.post('http://localhost:7001/addCard', cardStd)
      // let data = await res.json()
      console.log('row=', res.data.row)
    },
    clear () {
      this.card_code = ''
      this.ref_type = ''
      this.ref_code = ''
      this.is_active = ''
    },
  },
}
</script>