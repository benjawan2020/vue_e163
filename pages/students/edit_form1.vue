<template>
  <form>
    <v-text-field
      v-model="code"
      label="รหัส"
    />
    <v-text-field
      v-model="first_name"
      label="ชื่อ"
    />
    <v-text-field
      v-model="last_name"
      label="นามสกุล"
    />
    <v-text-field
      v-model="is_active"
      label="สถานะ"
    />
    <v-text-field
      v-model="img"
      label="ชื่อรูปภาพ"
    />
    <v-btn @click="save">
      บันทึก
    </v-btn>
    <v-btn>ลบหน้าจอ</v-btn>
  </form>
</template>
<script>
export default {
  data() {
    return {
      code: '',
      first_name: '',
      last_name: '',
      is_active: '',
      img: '',
    }
  },
  async created() {
    console.log(this.$route.query.code)
    let res = await this.$http.get('http://localhost:7001/editstde1?code=' + this.$route.query.code)
    console.log(res.data.row)
    this.code = res.data.row[0].code
    this.first_name = res.data.row[0].first_name
    this.last_name = res.data.row[0].last_name
    this.is_active = res.data.row[0].is_active
    this.img = res.data.row[0].img
  },
  methods: {
    async save(){
        let student = {
            code: this.code,
            pre_name: this.pre_name,
            first_name: this.first_name,
            last_name: this.last_name,
            is_active: this.is_active,
            img: this.img
        }
        console.log('std',student)
        let res = await this.$http.post('http://localhost:7001/insertel' , student)
        console.log(res.data)
    }
  },
}
</script>