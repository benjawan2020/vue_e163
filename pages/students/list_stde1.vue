<template>
    <div>
        <h1>show data student</h1>
        <ul>
          <li v-for="std in student" :key="std.code">
            <span>{{std.code}}</span>
            <span>{{std.pre_name}}</span>
            <span>{{std.first_name}}</span>
            <span>{{std.last_name}}</span>
            <span>{{std.is_active}}</span>
            <v-btn @click="edit(std.code)">EDIT</v-btn>
          </li>
        </ul>
    </div>
</template>
<script>
export default {
    data(){
        return{
          student: [
          {"code":"6201001","pre_name":"นาย","first_name":"สมชาย1","last_name":"สบายดี","is_active":"Y"},
          {"code":"6201002","pre_name":"นาย","first_name":"สมชาย2","last_name":"สบายดี","is_active":"Y"},
          ],
        }
    },
    async created() {
    let res = await this.$http.get('http://localhost:7001/liststd')
    console.log(res.data.row)
    this.student = res.data.row
  },
  methods: {
    edit(code){
    console.log(code)
    this.$router.push('edit_form1?code=' + code)
    }
  },
}
</script>