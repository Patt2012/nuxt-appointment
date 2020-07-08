<template>
    <div>
        <v-app-bar
            color="primary"
            dense
            flat
            dark
        >
        <v-toolbar-title>ลงทะเบียน</v-toolbar-title>
        </v-app-bar>
        <v-container class="pt-0 pb-0">
            <v-row>
                <v-col cols="12" class="mt-8 text-primart text-title text-center">
                  หน้าที่ 2 จาก 2
                </v-col>
                <v-col cols="12">
                    <v-form>
                      <p class="text-center text-main mb-0 mt-4">ข้อมูลเพิ่มเติม</p>
                      <v-text-field
                            v-model="form.email"
                            dense
                            label="Email"
                        ></v-text-field>
                        <v-text-field
                            v-model="form.phone"
                            dense
                            label="โทรศัพท์"
                        ></v-text-field>
                        <p class="text-center text-main mb-0 mt-4">ข้อมูลการนัดหมาย</p>
                        <!--วันที่-->
                        <v-dialog
                          ref="dialog"
                          v-model="modal"
                          persistent
                          width="290px"
                        >
                          <template v-slot:activator="{ on, attrs }">
                            <v-text-field
                              v-model="form.dateappoint"
                              label="วันที่"
                              prepend-icon="event"
                              readonly
                              v-bind="attrs"
                              v-on="on"
                              class="set-date"
                            ></v-text-field>
                          </template>
                          <v-date-picker
                            :min="new Date().toISOString().substr(0, 10)"
                            v-model="form.dateappoint"
                            scrollable
                            locale="th-TH"
                          >
                            <v-spacer></v-spacer>
                            <v-btn text color="primary" @click="modal = false">Cancel</v-btn>
                            <v-btn text color="primary" @click="$refs.dialog.save(date)">OK</v-btn>
                          </v-date-picker>
                        </v-dialog>
                        <!--เวลา-->
                        <v-btn rounded color="primary" dark class="w-100 mt-10 next-btn" @click="handleAdd">บันทึก</v-btn>
                        <div class="w-100 text-center next-btn text-primary" @click="handleBlack">ถอยกลับ</div>
                    </v-form>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>

<script>
export default {
  data(){
    return {
      form: {
        email: '',
        phone: '',
        dateappoint: new Date().toISOString().substr(0, 10),
        timeappoint: ''
      },
      modal: false,
    }
  },
  methods: {
    handleAdd(){
      console.log("Save")
    },
    handleBlack(){
      this.$router.push('/register')
    }
  }
}
</script>

<style lang="scss" scoped>
.v-form{
  padding: 0 10px;
}
.set-date{
  position: relative;
  ::v-deep .v-input__prepend-outer{
    position: absolute;
    right: 0;
  }
}
.set-time{
  position: relative;
  ::v-deep .v-input__prepend-outer{
    position: absolute;
    right: 0;
  }
}
</style>
