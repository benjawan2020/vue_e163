<template>
    <div>
        <h1>show data student</h1>
        <v-list-item
        v-for="std in student"
        :key="std.code"
        @click=""
      >
        <v-list-item-avatar>
          <v-img :src="'images/' + std.img"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title v-text="std.code"></v-list-item-title>
        </v-list-item-content>

        <v-list-item-content>
          <v-list-item-title v-text="std.pre_name"></v-list-item-title>
        </v-list-item-content>

        <v-list-item-content>
          <v-list-item-title v-text="std.first_name"></v-list-item-title>
        </v-list-item-content>

        <v-list-item-content>
          <v-list-item-title v-text="std.last_name"></v-list-item-title>
        </v-list-item-content>

        <v-list-item-content>
          <v-list-item-title v-text="std.is_active"></v-list-item-title>
        </v-list-item-content>

        <v-list-item-icon>
          <v-icon :color="std.is_active ? 'deep-purple accent-4' : 'grey'">chat_bubble</v-icon>
        </v-list-item-icon>
      </v-list-item>
    </v-list>

    </div>
</template>
<script>
export default {
    data(){
        return{
          student: [
          {'code':'6201001','pre_name':'นาย','first_name':'สมชาย1','last_name':'สบายดี','is_active':'Y', avatar: ''},
          {'code':'6201002','pre_name':'นาย','first_name':'สมชาย2','last_name':'สบายดี','is_active':'Y' ,avatar: ''},
          ],
        }
    },
 async created() {
    let res = await this.$http.get('http://localhost:7001/liststd')
    console.log(res.data.row)
    this.student = res.data.row
  },
}
</script>