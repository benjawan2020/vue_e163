<template>
  <div>
      <center>
       <v-icon size="200" color="teal darken-2">mdi-account-circle</v-icon>
    <h2>Hello: {{ name }}</h2>
    <h2>age: {{ age }}</h2>
    <input type="text" :value="name">
    <input type="text" v-model="name">
        <v-btn  color="success" dark button @click="doSave"> <v-icon color="pink">mdi-heart</v-icon> SAVE</v-btn><br><br>
        <v-btn  color="success" dark button @click="doMenu"> <v-icon  color="pink" dark>mdi-format-list-bulleted-square</v-icon> MENU</v-btn><br><br>
        <v-btn  color="success" dark button @click="doHome"> <v-icon color="pink">mdi-account-circle</v-icon> HOME</v-btn>
        </center>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: "Benjawan Singhaampol",
      age: 20,
    }
  },
  methods:{
    doSave(){
    console.log("DO SAVE");
    },
    doMenu(){
        this.$router.push('memu');
    },
    doHome(){
        this.$router.replace('/');
    },
  },
}
</script>