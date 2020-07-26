<template>
    <center>
        <div class="box2" style="padding-top: 20px;background: #E0E0E0;padding-bottom: 9%">
            <img src="images/ben.jpg" style="width: 90px;height: 100px;border-radius: 50%;" >

        <v-card style="padding-bottom: 30px;padding-top: 30px;background: #BDBDBD;">
            <v-text-field
            label="Username"
            prepend-icon="account_circle" color="#000000"
          ></v-text-field>

          <v-text-field
            label="Password"
            prepend-icon="account_box" color="#000000"
          ></v-text-field>

    

     <v-checkbox
          v-model="allowSpaces"
          label="Allow spaces"
        ></v-checkbox>
        
        

    

            <nuxt-link to="/pages3"> 
                <v-btn color="primary" dark style="width: 350px;">Sign in</v-btn>
            </nuxt-link>

        </v-card>
        </div>
    </center>
</template>
<script>
export default {
    layout:"pages_2",
}
</script>
