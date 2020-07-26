<template>
  <div class="box5">
    <h1>HELLO {{ first }}age:{{std}} </h1>
        <v-text-field
            label="ชื่อ-นามสกุล"
            prepend-icon="mdi-map-marker" color="#000000"
          ></v-text-field>

           <v-text-field
            filled
            label="ชื่อเล่น"
            prepend-icon="face" color="#000000"
          ></v-text-field>

          <v-text-field
            loading
            label="ที่อยู่"
            prepend-icon="featured_play_list" color="#FFEB3B"
          ></v-text-field><br>

  </div>
</template>
<script>
export default {
  data:function(){
    return{
     name:"benjawan",
     age:45,
     dep:"information  technology",
     first: "chaiyaphum"

    }
  }
}
</script>
<script>
export default {
    layout:"default1",
}
</script>