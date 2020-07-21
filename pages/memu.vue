<template>
  <v-container fluid class="pa-0">
        <div class="text-center">

          <div class="my-2">
            <nuxt-link to="/activity/row"> 
                <v-btn  color="primary" dark> <v-icon>mdi-account-circle</v-icon> กิจกรรมเข้าแถว</v-btn> 
            </nuxt-link>
             <nuxt-link to="/activity/homeroom"> 
                <v-btn  color="primary" dark><v-icon>mdi-account-circle</v-icon> กิจกรรมโฮมรูม</v-btn><br><br>
            </nuxt-link>
          </div>

          <div class="my-2">
            <nuxt-link to="/activity/special"> 
                <v-btn color="primary" dark> <v-icon>mdi-account-circle</v-icon> กิจกรรมพิเศษ</v-btn>
            </nuxt-link>    
            <nuxt-link to="/activity/flag"> 
                <v-btn color="primary" dark> <v-icon>mdi-account-circle</v-icon> กิจกรรมวิชาชีพ</v-btn><br><br>
            </nuxt-link> 
          </div>

          <div class="my-2">
            <nuxt-link to="/"> 
                <v-btn color="error" dark> <v-icon dark left>mdi-arrow-left</v-icon>กลับหน้าหลัก</v-btn>
            </nuxt-link>
          </div>
        </div>
  </v-container>
</template>