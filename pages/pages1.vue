<template>
    <center>
        <div style="color: #000;padding-top: 5%;" >
            <h1>Welcome!</h1>
            <h5>Lorem ipsum dolor sit amet,</h5>
            <h5>consectetur adipiscing elit.</h5>
        </div><br>

        <div class="box1" style="padding-top: -30px%;">
            <img src="images/ben.jpg" style="width: 250px;height: 320px;margin-top: -10px;" >
        </div><br><br><br>

            <nuxt-link to="/pages2"> 
                <v-btn color="primary" dark style="width: 350px;">Sign in</v-btn>
            </nuxt-link>


    </center>
</template>
<script>
export default {
    layout:"pages_1",
}
</script>

<style>
.box1 {
  background: #757575;
  width: 300px; 
  height: 300px;
}
</style>