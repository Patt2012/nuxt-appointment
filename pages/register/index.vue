<template>
    <div>
        <!--สร้างแถบ-->
        <v-app-bar
            color="primary"
            dense
            flat
            dark
        >
        <v-toolbar-title>ลงทะเบียน</v-toolbar-title>
        </v-app-bar>
        <!--ครอบด้วย container -->
        <!-- pt: padding-top, pb: padding-border-->
        <v-container class="pt-0 pb-0">
            <!--สร้างแถว-->
            <v-row>
                <!--สร้างคอลัมภ์เต็มหน้า-->
                <v-col cols="12" class="mt-8 text-primart text-title text-center">
                    <!--mt: margin-top-->
                    หน้าที่ 1 จาก 2
                </v-col>
                <!--ใสรูปภาพ-->
                <v-col cols="12" class="text-center pb-0">
                    <img src="~/assets/handwrite.png" alt="" width="155">
                </v-col>
                <v-col cols="12" class="text-center pt-2 pb-0">
                    Display name
                </v-col>
                <v-col cols="12">
                    <!--สร้างฟอร์ม-->
                    <v-form>
                        <v-text-field
                            v-model="form.firstname"
                            dense
                            label="ชื่อ"
                        ></v-text-field>
                        <v-text-field
                            v-model="form.lastname"
                            dense
                            label="นามสกุล"
                        ></v-text-field>
                        <div class="status-group d-flex mt-3">
                            <p>สถานะ</p>
                            <div class="circle" :class="form.status == 'ทนายความ' ? 'active' : ''" @click="handleStatus('ทนายความ')">
                              <svg viewBox="0 0 64 54" xmlns="http://www.w3.org/2000/svg"><title/><g data-name="59-woman" id="_59-woman"><path d="M28.01,54.99C29.13,57.32,30.47,59,32,59v4H13V44.25a3.994,3.994,0,0,1,3.18-3.92L24,38.75V41S25.45,49.69,28.01,54.99Z" style="fill:#414952"/><path d="M35.99,54.99C38.55,49.69,40,41,40,41V38.75l7.82,1.58A3.994,3.994,0,0,1,51,44.25V63H32V59C33.53,59,34.87,57.32,35.99,54.99Z" style="fill:#414952"/><path d="M28.01,54.99C25.45,49.69,24,41,24,41V38.75l-7.82,1.58A3.994,3.994,0,0,0,13,44.25v3a3.994,3.994,0,0,1,3.18-3.92L24,41.75V44s1.45,8.69,4.01,13.99C29.13,60.32,30.47,62,32,62V59C30.47,59,29.13,57.32,28.01,54.99Z" style="fill:#636978"/><path d="M47.82,40.33,40,38.75V41s-1.45,8.69-4.01,13.99C34.87,57.32,33.53,59,32,59v3c1.53,0,2.87-1.68,3.99-4.01C38.55,52.69,40,44,40,44V41.75l7.82,1.58A3.994,3.994,0,0,1,51,47.25v-3A3.994,3.994,0,0,0,47.82,40.33Z" style="fill:#636978"/><path d="M33,48l2.99,6.99C34.87,57.32,33.53,59,32,59s-2.87-1.68-3.99-4.01L31,48Z" style="fill:#ff7045"/><polygon points="35 46 33 48 31 48 29 46 32 43 35 46" style="fill:#ff7045"/><path d="M32,43l-3,3-5-5V38.75l2.33-.47a1.862,1.862,0,0,0,.69-.26Z" style="fill:#afb4c8"/><path d="M40,38.75V41l-5,5-3-3,4.98-4.98a1.862,1.862,0,0,0,.69.26Z" style="fill:#afb4c8"/><path d="M31,48l-2.99,6.99C25.45,49.69,24,41,24,41l5,5Z" style="fill:#e9edf5"/><path d="M40.73,14.9A10.271,10.271,0,0,1,38,17a2.938,2.938,0,0,0-3-3l-3,3c0-3-6-6-6-6l-3,4,.36,4H23a3,3,0,0,0,0,6h.91L24,26a8.014,8.014,0,0,0,2.34,5.66,7.838,7.838,0,0,0,1.69,1.28L28,33v2H25l-2-2-2,2a7.5,7.5,0,0,1-3-6V15a14,14,0,0,1,28,0V29a7.5,7.5,0,0,1-3,6l-2-2-2,2H36V33l-.03-.06A7.974,7.974,0,0,0,40,26l.09-1H41a3,3,0,0,0,0-6h-.36L41,15Z" style="fill:#b25e1e"/><path d="M24,26l-.09-1H23a2.982,2.982,0,0,1-2.224-1A2.99,2.99,0,0,0,23,29h.91L24,30a7.993,7.993,0,0,0,1.758,5H28V33l.03-.06a7.838,7.838,0,0,1-1.69-1.28A8.014,8.014,0,0,1,24,26Z" style="fill:#8e4a1b"/><path d="M40.09,29H41a2.99,2.99,0,0,0,2.224-5A2.982,2.982,0,0,1,41,25h-.91L40,26a7.974,7.974,0,0,1-4.03,6.94L36,33v2h2.237A7.956,7.956,0,0,0,40,30Z" style="fill:#8e4a1b"/><path d="M32,1A14,14,0,0,0,18,15v4a14,14,0,0,1,28,0V15A14,14,0,0,0,32,1Z" style="fill:#d1813b"/><path d="M41,19a3,3,0,0,1,0,6h-.91l.55-6Z" style="fill:#ffb680"/><path d="M23.91,25l-.55-6L23,15l3-4s6,3,6,6l3-3a2.938,2.938,0,0,1,3,3,10.271,10.271,0,0,0,2.73-2.1L41,15l-.36,4-.55,6L40,26a7.992,7.992,0,0,1-11.97,6.94,7.838,7.838,0,0,1-1.69-1.28A8.014,8.014,0,0,1,24,26Z" style="fill:#ffdaaa"/><path d="M26,14s6,3,6,6l3-3a2.938,2.938,0,0,1,3,3,10.271,10.271,0,0,0,2.73-2.1l.009,0L41,15l-.27-.1A10.271,10.271,0,0,1,38,17a2.938,2.938,0,0,0-3-3l-3,3c0-3-6-6-6-6l-3,4,.241,2.679Z" style="fill:#ffb680"/><path d="M35,46l5-5s-1.45,8.69-4.01,13.99L33,48Z" style="fill:#e9edf5"/><path d="M36.98,38.02,32,43l-4.98-4.98A1.946,1.946,0,0,0,28,36.31V33l.03-.06a7.964,7.964,0,0,0,7.94,0L36,33v3.31A1.946,1.946,0,0,0,36.98,38.02Z" style="fill:#ffb680"/><path d="M36,38v1l.98-.98A1.946,1.946,0,0,1,36,36.31Z" style="fill:#eb975d"/><path d="M32,37a7.954,7.954,0,0,0,3.97-1.06L36,36V33l-.03-.06a7.964,7.964,0,0,1-7.94,0L28,33v3l.03-.06A7.954,7.954,0,0,0,32,37Z" style="fill:#eb975d"/><path d="M28,38V36.31a1.946,1.946,0,0,1-.98,1.71L28,39Z" style="fill:#eb975d"/><path d="M23.36,19l.55,6H23a3,3,0,0,1,0-6Z" style="fill:#ffb680"/><path d="M36,35h3l2-2,2,2a7.5,7.5,0,0,0,3-6V15a14,14,0,0,0-28,0V29a7.5,7.5,0,0,0,3,6l2-2,2,2h3" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><path d="M36,33v3.31a1.946,1.946,0,0,0,.98,1.71,1.862,1.862,0,0,0,.69.26l2.33.47,7.82,1.58A3.994,3.994,0,0,1,51,44.25V63H13V44.25a3.994,3.994,0,0,1,3.18-3.92L24,38.75l2.33-.47a1.862,1.862,0,0,0,.69-.26A1.946,1.946,0,0,0,28,36.31V33" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><line style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px" x1="19" x2="19" y1="63" y2="50"/><line style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px" x1="45" x2="45" y1="63" y2="50"/><polyline points="37 38 36.98 38.02 32 43 27.02 38.02 27 38" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><polyline points="32 43 29 46 24 41 24 38.75 24 38" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><polyline points="32 43 35 46 40 41 40 38.75 40 38" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><polyline points="35 46 33 48 31 48 29 46" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><path d="M40,41s-1.45,8.69-4.01,13.99C34.87,57.32,33.53,59,32,59s-2.87-1.68-3.99-4.01C25.45,49.69,24,41,24,41" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><polyline points="33 48 35.99 54.99 36 55" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><polyline points="31 48 28.01 54.99 28 55" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><line style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px" x1="32" x2="32" y1="59" y2="63"/><path d="M40,19h1a3,3,0,0,1,0,6H40" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><path d="M24,19H23a3,3,0,0,0,0,6h1" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><path d="M41,15l-.36,4-.55,6L40,26a7.992,7.992,0,0,1-11.97,6.94,7.838,7.838,0,0,1-1.69-1.28A8.014,8.014,0,0,1,24,26l-.09-1-.55-6L23,15l3-4s6,3,6,6l3-3a2.938,2.938,0,0,1,3,3,10.271,10.271,0,0,0,2.73-2.1A4.415,4.415,0,0,0,42,12" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/></g></svg>
                            </div>
                             <p>ทนายความ</p>
                            <div class="circle" :class="form.status == 'คู่ความ' ? 'active' : ''" @click="handleStatus('คู่ความ')">
                              <svg viewBox="0 0 64 54" xmlns="http://www.w3.org/2000/svg"><title/><g data-name="54-woman" id="_54-woman"><circle cx="32" cy="47" r="2" style="fill:#b25e1e"/><path d="M35.97,32.94l1.69-1.28A8.014,8.014,0,0,0,40,26v-.9a10.682,10.682,0,0,0,2,.9h3.24A32.172,32.172,0,0,0,45,30v5l-3-3-3,3H36V33Z" style="fill:#704021"/><path d="M28.03,32.94,28,33v2H25l-3-3-3,3V30a31.044,31.044,0,0,0-.15-3.12C21.24,26.2,22.32,22.6,23,19l1,7A7.974,7.974,0,0,0,28.03,32.94Z" style="fill:#704021"/><path d="M40,25.1C32.83,21.01,31.84,10,30,10a1.959,1.959,0,0,0-2,2,4.38,4.38,0,0,0-3-1c-1,0-1.25,4-2,8-.68,3.6-1.76,7.2-4.15,7.88A79.119,79.119,0,0,1,18,15a14,14,0,0,1,28,0,69.667,69.667,0,0,1-.76,11H42A10.682,10.682,0,0,1,40,25.1Z" style="fill:#b25e1e"/><path d="M45.24,22H42a10.682,10.682,0,0,1-2-.9C32.83,17.01,31.84,6,30,6a1.959,1.959,0,0,0-2,2,4.38,4.38,0,0,0-3-1c-1,0-1.25,4-2,8-.68,3.6-1.76,7.2-4.15,7.88-.232-2.358-.664-4.311-.8-8.793-.02.3-.046.605-.046.913a79.119,79.119,0,0,0,.85,11.88C21.24,26.2,22.32,22.6,23,19c.75-4,1-8,2-8a4.38,4.38,0,0,1,3,1,1.959,1.959,0,0,1,2-2c1.84,0,2.83,11.01,10,15.1a10.682,10.682,0,0,0,2,.9h3.24A69.667,69.667,0,0,0,46,15c0-.3-.026-.6-.046-.9A69.863,69.863,0,0,1,45.24,22Z" style="fill:#d1813b"/><path d="M28,35V33l.03-.06A7.853,7.853,0,0,0,32,34a7.954,7.954,0,0,0,3.97-1.06L36,33v3.31a1.962,1.962,0,0,0,.44,1.25L32,42l-4.44-4.44A1.962,1.962,0,0,0,28,36.31Z" style="fill:#ffb680"/><path d="M36,38l.44-.44A1.962,1.962,0,0,1,36,36.31Z" style="fill:#eb975d"/><path d="M32,37a7.954,7.954,0,0,0,3.97-1.06L36,36V33l-.03-.06A7.954,7.954,0,0,1,32,34a7.853,7.853,0,0,1-3.97-1.06L28,33v3l.03-.06A7.853,7.853,0,0,0,32,37Z" style="fill:#eb975d"/><path d="M28,36.31a1.962,1.962,0,0,1-.44,1.25L28,38Z" style="fill:#eb975d"/><rect height="6" style="fill:#ffb680" width="6" x="45" y="57"/><rect height="6" style="fill:#ffb680" width="6" x="13" y="57"/><path d="M40,25.1V26a8.014,8.014,0,0,1-2.34,5.66l-1.69,1.28A7.954,7.954,0,0,1,32,34a7.853,7.853,0,0,1-3.97-1.06A7.974,7.974,0,0,1,24,26l-1-7c.75-4,1-8,2-8a4.38,4.38,0,0,1,3,1,1.959,1.959,0,0,1,2-2C31.84,10,32.83,21.01,40,25.1Z" style="fill:#ffdaaa"/><path d="M30,10a1.959,1.959,0,0,0-2,2,4.38,4.38,0,0,0-3-1c-1,0-1.25,4-2,8l.236,1.652C23.815,17.149,24.113,14,25,14a4.38,4.38,0,0,1,3,1,1.959,1.959,0,0,1,2-2c1.818,0,2.811,10.745,9.751,14.946A7.951,7.951,0,0,0,40,26v-.9C32.83,21.01,31.84,10,30,10Z" style="fill:#ffb680"/><path d="M32,45a2,2,0,1,0,2,2A2.006,2.006,0,0,0,32,45ZM45,57v6H19V57H13V44.25a3.994,3.994,0,0,1,3.18-3.92l10.15-2.05a1.993,1.993,0,0,0,1.23-.72L32,42l4.44-4.44a1.993,1.993,0,0,0,1.23.72l10.15,2.05A3.994,3.994,0,0,1,51,44.25V57Z" style="fill:#e9edf5"/><path d="M32,52a1.991,1.991,0,0,0,1.307-3.5,1.958,1.958,0,0,1-2.614,0A1.991,1.991,0,0,0,32,52Z" style="fill:#afb4c8"/><path d="M47.82,40.33,37.67,38.28a1.993,1.993,0,0,1-1.23-.72L32,42l-4.44-4.44a1.993,1.993,0,0,1-1.23.72L16.18,40.33A3.994,3.994,0,0,0,13,44.25v3a3.994,3.994,0,0,1,3.18-3.92l10.15-2.05a1.993,1.993,0,0,0,1.23-.72L32,45l4.44-4.44a1.993,1.993,0,0,0,1.23.72l10.15,2.05A3.994,3.994,0,0,1,51,47.25v-3A3.994,3.994,0,0,0,47.82,40.33Z" style="fill:#afb4c8"/><path d="M23,19l1,7a7.974,7.974,0,0,0,4.03,6.94A7.853,7.853,0,0,0,32,34a7.954,7.954,0,0,0,3.97-1.06l1.69-1.28A8.014,8.014,0,0,0,40,26V25" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><path d="M36,33v3.31a1.962,1.962,0,0,0,.44,1.25,1.993,1.993,0,0,0,1.23.72l10.15,2.05A3.994,3.994,0,0,1,51,44.25V63H13V44.25a3.994,3.994,0,0,1,3.18-3.92l10.15-2.05a1.993,1.993,0,0,0,1.23-.72A1.962,1.962,0,0,0,28,36.31V33" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><polyline points="19 63 19 57 19 50" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><polyline points="45 63 45 57 45 50" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><path d="M28,35H25l-3-3-3,3V30a31.044,31.044,0,0,0-.15-3.12A79.119,79.119,0,0,1,18,15a14,14,0,0,1,28,0,69.667,69.667,0,0,1-.76,11A32.172,32.172,0,0,0,45,30v5l-3-3-3,3H36" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><line style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px" x1="51" x2="45" y1="57" y2="57"/><line style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px" x1="19" x2="13" y1="57" y2="57"/><path d="M46,26H42a10.682,10.682,0,0,1-2-.9C32.83,21.01,31.84,10,30,10a1.959,1.959,0,0,0-2,2,4.38,4.38,0,0,0-3-1c-1,0-1.25,4-2,8-.68,3.6-1.76,7.2-4.15,7.88A2.96,2.96,0,0,1,18,27" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><polyline points="27 37 27.56 37.56 32 42 36.44 37.56 37 37" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/><line style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px" x1="32" x2="32" y1="42" y2="45"/><circle cx="32" cy="47" r="2" style="fill:none;stroke:#000;stroke-linejoin:round;stroke-width:2px"/></g></svg>
                            </div>
                             <p>คู่ความ</p>
                        </div>
                        <v-btn rounded color="primary" dark class="w-100 mt-10 next-btn" @click="handleNextPage">หน้าถัดไป</v-btn>
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
                firstname: this.$store.getters.getRegister.firstname,
                lastname: this.$store.getters.getRegister.lastname,
                status: this.$store.getters.getRegister.status
            }
        }
    },
    methods: {
        /*เลือกปุ่มสถานะ*/
        handleStatus(status){
            this.form.status = status
        },
        validate(){
            let validated = true
            const errors = []
            const validatorField = [
                'firstname',
                'lastname',
            ]
            validatorField.forEach((field) => {
                if(this.form[field] == ''){
                    validated = false
                    errors.push(`${field} can not be null`)
                }
            })
            if(!validated){
                this.$store.dispatch('setDialog', {
                    isShow: true,
                    title: 'แจ้งข้อผิดพลาด',
                    message: errors.map((error) => error+'<br/>').join('')
                })
            }
            return validated
        },
        /*กดปุ่มหน้าถัดไป*/
        handleNextPage(){
            if(this.validate()){
                this.$store.dispatch('setRegister', this.form)
                this.$router.push('/register/appoint')
            }
        }
    }
}
</script>

<style lang="scss" scoped>
    .v-form{
        padding: 0 10px;
    }
    .status-group{
        p{
            margin-bottom: 0;
            align-self: center;
            margin-right: 20px;
        }
        .circle{
            width: 45px;
            height: 45px;
            color: #FFF;
            border-radius: 50%;
            position: relative;
            /*ทำให้ปุ่มเป็นสีเทา*/
            background: rgba($color: #000000, $alpha: 0.3);
            margin-right: 7px;
            &.active{
                background: #1a56be;
            }
        }
        svg{
            position: absolute;
            top: 30%;
            height: 80%;
            transform: translate(4%, -30%);
        }
    }
</style>
