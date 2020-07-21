<template>
 <v-card
    color="blue darken-4"
    dark
    height="500"
    width="500"
    class="mx-auto"
  >
    <v-card-title class="blue darken-3">
      สมัครสมาชิก<v-icon size="40">assignment_ind</v-icon>
    </v-card-title>


     <v-card-text>
       <v-form>
         <v-text-field  prepend-icon="mdi-account-circle" label="ชื่อ" />
         <v-text-field  prepend-icon="perm_contact_calendar" label="นามสกุล" />
         <v-text-field type="date" prepend-icon="date_range" label="วัน/เดือน/ปีเกิด" />
         <v-text-field  prepend-icon="sd_card" label="เลขบัตรประจำตัวประชาชน" />
         <v-text-field type="file" prepend-icon="perm_media" label="รูปภาพ" />

       </v-form>
     </v-card-text>

     <v-card-actions>
        <nuxt-link to="/register">
            <v-btn class="success">ตกลง</v-btn> </nuxt-link>
             <v-spacer></v-spacer>
            <v-btn color="error">ยกเลิก</v-btn>
     </v-card-actions>

   </v-card>
</template>