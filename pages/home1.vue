<template>
    <div class="box6" style="padding-top: 11px;">
        <v-container>
            <center>
                    <img src="../img/ben.jpg" width="230" height="230" style="border-radius: 50%;" >

                <v-card  style=" border-radius: 10px;background: #424242;">
                    <font Face="TH SarabunPSK" style="font-size: 35px;"><b><u>ประวัติส่วนตัว</u></b></font><br>
                    <p >ชื่อนางสาวเบญจวรรณ สิงหอำพล ชื่อเล่น เบญเท็น </p>
                    <p>เกิดวันที่ 20 มิถุนายน พ.ศ2543 อายุ 20 ปี</p>
                    <p>กำลังศึกษาที่วิทยาลัยเทคนิคชัยภูมิ แผนกเทคโนโลยีสารสนเทศ</p>
                    <p>ที่อยู่ บ้านเอื้ออาทร บ้านเลขที่21/78 ต.ในเมือง อ.เมือง จ.ชัยภูมิ</p>
                </v-card>

                <center>
                    <nuxt-link to="/home"> 
                        <v-btn rounded color="error" dark>กลับหน้า Home</v-btn><br><br>
                    </nuxt-link>
                </center>

            </center>
        </v-container>
    </div>
</template>

<script>
export default {
    layout:"default2",
}
</script>