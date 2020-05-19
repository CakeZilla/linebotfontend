<template >
  <div class>
    <b-card
      overlay
      img-src="https://scontent.fbkk8-2.fna.fbcdn.net/v/t1.15752-9/97785816_1270972696437980_4729290817221427200_n.png?_nc_cat=107&_nc_sid=b96e70&_nc_eui2=AeF8CDTWpHHxuI4IJqoumFJacsJjVKSFXuFywmNUpIVe4VwUoOEidDgbBEtRkVtLvtqdLw9fUvEI43bEnmIyLtve&_nc_ohc=2tqyZXbncs0AX9By_dn&_nc_ht=scontent.fbkk8-2.fna&oh=caa250138fcb00455892e77fe4e799d8&oe=5EDFA36B"
      img-alt
      text-variant="white"
      title
      sub-title
    ></b-card>
    <div>
      <div>
        <b-card>
          <!-- โรคเบาหวาน         -->
          <b-button v-b-toggle="'collapse-1'" block variant="outline-primary" class="m-1">โรคเบาหวาน</b-button>
          <b-collapse id="collapse-1">
            <b-card>
              <h5>วันที่ทำเเบบสอบถาม</h5>
              <b-form-datepicker id="example-datepicker" v-model="DATE" class="mb-2"></b-form-datepicker>
              <h4>
                <b>เเบบสอบถาม โรคเบาหวาน</b>
              </h4>
              <b-form-group>
                <b-form-radio
                  v-model="EAT"
                  value="งดอาหารก่อนมาตรวจมากกว่า 8 ชั่วโมง"
                >งดอาหารก่อนมาตรวจมากกว่า 8 ชั่วโมง</b-form-radio>
                <b-form-radio v-model="EAT" value="ไม่ได้งดอาหารก่อนตรวจ">ไม่ได้งดอาหารก่อนตรวจ</b-form-radio>
              </b-form-group>
              <h5>
                ระดับน้ำตาลจากปลายนิ้ว
                <b-form-input v-model="FBS" class="m-1"></b-form-input>มิลลิกรัมเปอร์เซ็นต์
              </h5>
              <b-button pill variant="success" @click="adddm">ยืนยัน</b-button>
            </b-card>
          </b-collapse>
          <!-- โรคความดันโลหิตสูง -->
          <b-button
            v-b-toggle="'collapse-2'"
            block
            variant="outline-primary"
            class="m-1"
          >โรคความดันโลหิตสูง</b-button>
          <b-collapse id="collapse-2">
            <b-card>
              <h5>วันที่ทำเเบบสอบถาม</h5>
              <b-form-datepicker id="example-datepicker" v-model="DATE" class="mb-2"></b-form-datepicker>
              <h4>
                <b>เเบบสอบถาม โรคความดันโลหิตสูง</b>
              </h4>
              <h5>
                ตัวบน (SBP)
                <b-form-input v-model="SBP" class="m-1"></b-form-input>มิลลิเมตรปรอท
              </h5>
              <h5>
                ตัวล่าง (DBP)
                <b-form-input v-model="DBP" class="m-1"></b-form-input>มิลลิเมตรปรอท
              </h5>
              <b-button pill variant="success" @click="addht">ยืนยัน</b-button>
            </b-card>
          </b-collapse>
          <!-- ภาวะซึมเศร้า (2Q)           -->
          <b-button
            v-b-toggle="'collapse-3'"
            block
            variant="outline-primary"
            class="m-1"
          >ภาวะซึมเศร้า (2Q)</b-button>
          <b-collapse id="collapse-3">
            <b-card>
              <h5>วันที่ทำเเบบสอบถาม</h5>
              <b-form-datepicker id="example-datepicker" v-model="DATE" class="mb-2"></b-form-datepicker>
              <h4>
                <b>เเบบสอบถาม ภาวะซึมเศร้า (2Q)</b>
              </h4>
              <h5>1. ใน 2 สัปดาห์ที่ผ่านมารวมวันนี้ท่านรู้สึกหดหู่ เศร้าหรือท้อเเท้สิ้นหวัง หรือไม่</h5>
              <b-form-group>
                <b-form-radio v-model="DISMAL" value="ไม่มี">ไม่มี</b-form-radio>
                <b-form-radio v-model="DISMAL" value="มี">มี</b-form-radio>
              </b-form-group>
              <h5>2. ใน 2 สัปดาห์ที่ผ่านมารวมวันนี้ท่านรู้สึกเบื่อ ทำอะไรก็ไม่เพลิดเพลิน หรือไม่</h5>
              <b-form-group>
                <b-form-radio v-model="BORED" value="ไม่มี">ไม่มี</b-form-radio>
                <b-form-radio v-model="BORED" value="มี">มี</b-form-radio>
              </b-form-group>
              <b-button pill variant="success" @click="add2q">ยืนยัน</b-button>
            </b-card>
          </b-collapse>
          <!-- สุขภาพช่องปากเเละฟัน -->
          <b-button
            v-b-toggle="'collapse-4'"
            block
            variant="outline-primary"
            class="m-1"
          >สุขภาพช่องปากเเละฟัน</b-button>
          <b-collapse id="collapse-4">
            <b-card>
              <h5>วันที่ทำเเบบสอบถาม</h5>
              <b-form-datepicker id="example-datepicker" v-model="DATE" class="mb-2"></b-form-datepicker>
              <h4>
                <b>เเบบสอบถาม สุขภาพช่องปากเเละฟัน</b>
              </h4>
              <h5>1. ใบริเวณริมฝีปาก กระพุ้งเเก้ม ลิ้น มีปุ่ม/มีก้อนเนื้อ/มีเเผลเรื้อรัง หรือไม่</h5>
              <b-form-group>
                <b-form-radio v-model="LIPS" value="ไม่มี">ไม่มี</b-form-radio>
                <b-form-radio v-model="LIPS" value="มี">มี</b-form-radio>
              </b-form-group>
              <h5>2. บริเวณเหงือกมีเลือดออก/มีฝีหนอง/ฟันโยก หรือไม่</h5>
              <b-form-group>
                <b-form-radio v-model="GUMS" value="ไม่มี">ไม่มี</b-form-radio>
                <b-form-radio v-model="GUMS" value="มี">มี</b-form-radio>
              </b-form-group>
              <h5>3. มีฟันผุ เป็นรุ เสียวฟัน ฟันหัก ฟันเเตกเหลือเเต่ตอฟัน หรือไม่</h5>
              <b-form-group>
                <b-form-radio v-model="TEETH" value="ไม่มี">ไม่มี</b-form-radio>
                <b-form-radio v-model="TEETH" value="มี">มี</b-form-radio>
              </b-form-group>
              <h5>4. มีปัญหาการเคี้ยวอาหาร/การกลืน หรือไม่</h5>
              <b-form-group>
                <b-form-radio v-model="CHEW" value="ไม่มี">ไม่มี</b-form-radio>
                <b-form-radio v-model="CHEW" value="มี">มี</b-form-radio>
              </b-form-group>
              <h5>5. จำเป็นต้องใส่ฟันเทียม หรือทำฟันเทียมใหม่ หรือไม่</h5>
              <b-form-group>
                <b-form-radio v-model="ARTIFICIALTEETH" value="ไม่มี">ไม่มี</b-form-radio>
                <b-form-radio v-model="ARTIFICIALTEETH" value="มี">มี</b-form-radio>
              </b-form-group>
              <b-button pill variant="success" @click="addoral">ยืนยัน</b-button>
            </b-card>
          </b-collapse>
          <!-- ภาวะโภชนาการ -->
          <b-button
            v-b-toggle="'collapse-5'"
            block
            variant="outline-primary"
            class="m-1"
          >ภาวะโภชนาการ</b-button>
          <b-collapse id="collapse-5">
            <b-card>
              <h5>วันที่ทำเเบบสอบถาม</h5>
              <b-form-datepicker id="example-datepicker" v-model="DATE" class="mb-2"></b-form-datepicker>
              <h4>
                <b>เเบบสอบถาม ภาวะโภชนาการ</b>
              </h4>
              <h5>
                ค่าดัชนีมวลกาย
                <b-form-input v-model="BMI" class="m-1"></b-form-input>
              </h5>
              <h5>
                น้ำหนัก
                <b-form-input v-model="WAIGHT" class="m-1"></b-form-input>
              </h5>
              <h5>
                ส่วนสูง
                <b-form-input v-model="HIGH" class="m-1"></b-form-input>
              </h5>
              <b-button pill variant="success" @click="addnutritional">ยืนยัน</b-button>
            </b-card>
          </b-collapse>
          <!-- สุขภาวะทางตา -->
          <b-button
            v-b-toggle="'collapse-6'"
            block
            variant="outline-primary"
            class="m-1"
          >สุขภาวะทางตา</b-button>
          <b-collapse id="collapse-6">
            <b-card>
              <h5>วันที่ทำเเบบสอบถาม</h5>
              <b-form-datepicker id="example-datepicker" v-model="DATE" class="mb-2"></b-form-datepicker>
              <h4>
                <b>เเบบสอบถาม สุขภาวะทางตา</b>
              </h4>
              <h5>1. นับนิ้วในระยะ 3 เมตร ได้ถูกต้องน้อยกว่า 3 ใน 4 ครั้ง</h5>
              <b-form-group>
                <b-form-radio v-model="INCHCOUNT" value="ใช่">ใช่</b-form-radio>
                <b-form-radio v-model="INCHCOUNT" value="ไม่ใช่">ไม่ใช่</b-form-radio>
              </b-form-group>
              <h5>2. อ่านหนังสือพิมพ์หน้าหนึ่งในระยะ 1 ฟุต ไม่ได้</h5>
              <b-form-group>
                <b-form-radio v-model="READ" value="ใช่">ใช่</b-form-radio>
                <b-form-radio v-model="READ" value="ไม่ใช่">ไม่ใช่</b-form-radio>
              </b-form-group>
              <h5>3. ปิดตาดูทีละข้าง พบว่า ตามัวคล้ายมีหนองบัง</h5>
              <b-form-group>
                <b-form-radio v-model="AMBLYOPIA" value="ใช่">ใช่</b-form-radio>
                <b-form-radio v-model="AMBLYOPIA" value="ไม่ใช่">ไม่ใช่</b-form-radio>
              </b-form-group>
              <h5>4. ปิดตาดูทีละข้าง พบว่า มองเห็นชัดตรงกลาง ไม่เห็นรอบข้างหรือมักเดินชนประตู สิ่งของบ่อยๆ</h5>
              <b-form-group>
                <b-form-radio v-model="CLEARLYSEE" value="ใช่">ใช่</b-form-radio>
                <b-form-radio v-model="CLEARLYSEE" value="ไม่ใช่">ไม่ใช่</b-form-radio>
              </b-form-group>
              <h5>5. ปิดตาดูทีละข้าง พบว่า มองเห็นจุดดำกลางภาพ หรือเห็นภาพบิดเบี้ยว</h5>
              <b-form-group>
                <b-form-radio v-model="SPOTS" value="ใช่">ใช่</b-form-radio>
                <b-form-radio v-model="SPOTS" value="ไม่ใช่">ไม่ใช่</b-form-radio>
              </b-form-group>
              <b-button pill variant="success" @click="addeye">ยืนยัน</b-button>
            </b-card>
          </b-collapse>
          <!-- ความสามารถในการทำกิจวัตร -->
          <b-button
            v-b-toggle="'collapse-7'"
            block
            variant="outline-primary"
            class="m-1"
          >ความสามารถในการทำกิจวัตร</b-button>
          <b-collapse id="collapse-7">
            <b-card>
              <h5>วันที่ทำเเบบสอบถาม</h5>
              <b-form-datepicker id="example-datepicker" v-model="DATE" class="mb-2"></b-form-datepicker>
              <h4>
                <b>เเบบสอบถาม ความสามารถในการทำกิจวัตร</b>
              </h4>
              <h5>
                <b>ให้คะเเนน 2</b> ถ้าทำได้ด้วยตัวเอง
              </h5>
              <h5>
                <b>ให้คะเเนน 1</b> ถ้าทำได้เองบ้างเเต่ต้องการความช่วยเหลือบางสิ่ง
              </h5>
              <h5>
                <b>ให้คะเเนน 0</b> ถ้าไม่สามารถช่วยตัวเองได้
              </h5>
              <br />
              <h5>1. การรับประทานอาหาร</h5>
              <b-form-group>
                <b-form-radio v-model="EATING" value="0">0 คะเเนน</b-form-radio>
                <b-form-radio v-model="EATING" value="1">1 คะเเนน</b-form-radio>
                <b-form-radio v-model="EATING" value="2">2 คะเเนน</b-form-radio>
              </b-form-group>
              <h5>2. ล้างหน้า หวีผม เเปรงฟัน</h5>
              <b-form-group>
                <b-form-radio v-model="FACE" value="0">0 คะเเนน</b-form-radio>
                <b-form-radio v-model="FACE" value="1">1 คะเเนน</b-form-radio>
                <b-form-radio v-model="FACE" value="2">2 คะเเนน</b-form-radio>
              </b-form-group>
              <h5>3. ใช้ห้องน้ำ</h5>
              <b-form-group>
                <b-form-radio v-model="USETOILET" value="0">0 คะเเนน</b-form-radio>
                <b-form-radio v-model="USETOILET" value="1">1 คะเเนน</b-form-radio>
                <b-form-radio v-model="USETOILET" value="2">2 คะเเนน</b-form-radio>
              </b-form-group>
              <h5>4. การอาบน้ำ</h5>
              <b-form-group>
                <b-form-radio v-model="BATHE" value="0">0 คะเเนน</b-form-radio>
                <b-form-radio v-model="BATHE" value="1">1 คะเเนน</b-form-radio>
                <b-form-radio v-model="BATHE" value="2">2 คะเเนน</b-form-radio>
              </b-form-group>
              <h5>5. การสวมเสื้อผ้า</h5>
              <b-form-group>
                <b-form-radio v-model="GARB" value="0">0 คะเเนน</b-form-radio>
                <b-form-radio v-model="GARB" value="1">1 คะเเนน</b-form-radio>
                <b-form-radio v-model="GARB" value="2">2 คะเเนน</b-form-radio>
              </b-form-group>
              <h5>6. ลุกจากที่ หรือลุกจากเตียงไปยังเก้าอี้</h5>
              <b-form-group>
                <b-form-radio v-model="GETUG" value="0">0 คะเเนน</b-form-radio>
                <b-form-radio v-model="GETUG" value="1">1 คะเเนน</b-form-radio>
                <b-form-radio v-model="GETUG" value="2">2 คะเเนน</b-form-radio>
              </b-form-group>
              <h5>7. การเคลื่อนที่ภายในห้อง หรือบ้าน</h5>
              <b-form-group>
                <b-form-radio v-model="MOVE" value="0">0 คะเเนน</b-form-radio>
                <b-form-radio v-model="MOVE" value="1">1 คะเเนน</b-form-radio>
                <b-form-radio v-model="MOVE" value="2">2 คะเเนน</b-form-radio>
              </b-form-group>
              <h5>8. การขึ้นลงบันได้ 1 ชั้น</h5>
              <b-form-group>
                <b-form-radio v-model="DOWNSTAIRS" value="0">0 คะเเนน</b-form-radio>
                <b-form-radio v-model="DOWNSTAIRS" value="1">1 คะเเนน</b-form-radio>
                <b-form-radio v-model="DOWNSTAIRS" value="2">2 คะเเนน</b-form-radio>
              </b-form-group>
              <h5>9. การกลั้นการถ่ายอุจจาระ (ใน 1 สัปดาห์ที่ผ่านมา)</h5>
              <b-form-group>
                <b-form-radio v-model="WFECES" value="0">0 คะเเนน</b-form-radio>
                <b-form-radio v-model="WFECES" value="1">1 คะเเนน</b-form-radio>
                <b-form-radio v-model="WFECES" value="2">2 คะเเนน</b-form-radio>
              </b-form-group>
              <h5>10. การกลั้นปัสสาวะ (ใน 1 สัปดาห์ที่ผ่านมา)</h5>
              <b-form-group>
                <b-form-radio v-model="WURINE" value="0">0 คะเเนน</b-form-radio>
                <b-form-radio v-model="WURINE" value="1">1 คะเเนน</b-form-radio>
                <b-form-radio v-model="WURINE" value="2">2 คะเเนน</b-form-radio>
              </b-form-group>
              <b-button pill variant="success" @click="addadl">ยืนยัน</b-button>
            </b-card>
          </b-collapse>
          <!-- คัดกรองข้อเข่าเสื่อม  -->
          <b-button
            v-b-toggle="'collapse-8'"
            block
            variant="outline-primary"
            class="m-1"
          >คัดกรองข้อเข่าเสื่อม</b-button>
          <b-collapse id="collapse-8">
            <b-card>
              <h5>วันที่ทำเเบบสอบถาม</h5>
              <b-form-datepicker id="example-datepicker" v-model="DATE" class="mb-2"></b-form-datepicker>
              <h4>
                <b>เเบบสอบถาม คัดกรองข้อเข่าเสื่อม</b>
              </h4>
              <h5>มีอาการปวดเข่าหรือไม่</h5>
              <b-form-group>
                <b-form-radio v-model="KNEEPAIN" value="ไม่ปวดเข่า">ไม่ปวดเข่า</b-form-radio>
                <b-form-radio v-model="KNEEPAIN" value="ปวดเข่า">ปวดเข่า</b-form-radio>
              </b-form-group>
              <b-button pill variant="success" @click="addosteoarthritis">ยืนยัน</b-button>
            </b-card>
          </b-collapse>
          <!-- อุบัติเหตุ/ภาวะหกล้ม           -->
          <b-button
            v-b-toggle="'collapse-9'"
            block
            variant="outline-primary"
            class="m-1"
          >อุบัติเหตุ/ภาวะหกล้ม</b-button>
          <b-collapse id="collapse-9">
            <b-card>
              <h5>วันที่ทำเเบบสอบถาม</h5>
              <b-form-datepicker id="example-datepicker" v-model="DATE" class="mb-2"></b-form-datepicker>
              <h4>
                <b>เเบบสอบถาม อุบัติเหตุ/ภาวะหกล้ม</b>
              </h4>
              <h5>(ควรระมัดระวัง ผู้สูงอายุหกล้ม ขณะทดสอบ)</h5>
              <b-form-group>
                <b-form-radio v-model="WALKTIME" value="จับเวลาได้">
                  จับเวลาได้
                  <p>
                    <b-form-input v-model="TIME"></b-form-input>นาที:วินาที
                  </p>
                </b-form-radio>
                <b-form-radio v-model="WALKTIME" value="เดินไม่ได้">
                  เดินไม่ได้ (ระบุเหตุผล)
                  <b-form-input v-model="REASON"></b-form-input>
                </b-form-radio>
              </b-form-group>

              <b-button pill variant="success" @click="addtugt">ยืนยัน</b-button>
            </b-card>
          </b-collapse>
          <!-- การกลั้นปัสสาวะ           -->
          <b-button
            v-b-toggle="'collapse-10'"
            block
            variant="outline-primary"
            class="m-1"
          >การกลั้นปัสสาวะ</b-button>
          <b-collapse id="collapse-10">
            <b-card>
              <h5>วันที่ทำเเบบสอบถาม</h5>
              <b-form-datepicker id="example-datepicker" v-model="DATE" class="mb-2"></b-form-datepicker>
              <h4>
                <b>เเบบสอบถาม การกลั้นปัสสาวะ</b>
              </h4>
              <h5>
                <b>มีปัสสาวะเล็ด</b> หรือ
                <b>ปัสสาวะราด</b> จนทำให้เกิดปัญหาในการใช้ชีวิตประจำวัน
              </h5>
              <b-form-group>
                <b-form-radio v-model="UURINE" value="ไม่มี">ไม่มี</b-form-radio>
                <b-form-radio v-model="UURINE" value="มี">มี</b-form-radio>
              </b-form-group>
              <b-button pill variant="success" @click="addurine">ยืนยัน</b-button>
            </b-card>
          </b-collapse>
          <!-- ปัญหาการนอน           -->
          <b-button
            v-b-toggle="'collapse-11'"
            block
            variant="outline-primary"
            class="m-1"
          >ปัญหาการนอน</b-button>
          <b-collapse id="collapse-11">
            <b-card>
              <h5>วันที่ทำเเบบสอบถาม</h5>
              <b-form-datepicker id="example-datepicker" v-model="DATE" class="mb-2"></b-form-datepicker>
              <h4>
                <b>เเบบสอบถาม ปัญหาการนอน</b>
              </h4>
              <h5>1.มีปัญหาการนอนหลับ</h5>
              <b-form-group>
                <b-form-radio v-model="NAP" value="ไม่มี">ไม่มี</b-form-radio>
                <b-form-radio v-model="NAP" value="มีปัญหา">
                  มีปัญหา
                  <b-form-group>
                    <b-form-radio v-model="NNAP" value="นอนไม่หลับ">นอนไม่หลับ</b-form-radio>
                    <b-form-radio v-model="NNAP" value="นอนมากไป">นอนมากไป</b-form-radio>
                    <b-form-radio v-model="NNAP" value="นอนกรน">นอนกรน</b-form-radio>
                    <b-form-radio v-model="NNAP" value="นอนละเมอ">นอนละเมอ</b-form-radio>
                  </b-form-group>
                  <h6>
                    อื่นๆ
                    <b-form-input v-model="NNAP" ></b-form-input>
                  </h6>
                  <h6>
                    ระยะเวลาที่มีปัญหาในการนอนหลับ
                    <b-form-input v-model="TIMENAP"></b-form-input>ปี/เดือน
                  </h6>
                </b-form-radio>
              </b-form-group>
              <h5>2.มีอาการง่วง อ่อนเพลีย ตอนกลางวันหรือไม่ขณะนี้เวลาอะไร</h5>
              <b-form-group>
                <b-form-radio v-model="TIRED" value="ไม่มี">ไม่มี</b-form-radio>
                <b-form-radio v-model="TIRED" value="มีปัญหา">มีปัญหา</b-form-radio>
              </b-form-group>
              <b-button pill variant="success" @click="addsleep">ยืนยัน</b-button>
            </b-card>
          </b-collapse>
        </b-card>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data: () => ({
    //dm
    DATE: '',
    EAT: '',
    FBS: '',
    //ht
    SBP: '',
    DBP: '',
    //2q
    DISMAL: '',
    BORED: '',
    //oral
    LIPS: '',
    GUMS: '',
    TEETH: '',
    CHEW: '',
    ARTIFICIALTEETH: '',
    //nutritional
    BMI: '',
    WAIGHT: '',
    HIGH: '',
    //eye
    INCHCOUNT: '',
    READ: '',
    AMBLYOPIA: '',
    CLEARLYSEE: '',
    SPOTS: '',
    //adl
    EATING: '',
    FACE: '',
    USETOILET: '',
    BATHE: '',
    GARB: '',
    GETUG: '',
    MOVE: '',
    DOWNSTAIRS: '',
    WFECES: '',
    WURINE: '',
    //osteoarthritis
    KNEEPAIN: '',
    //tugt
    WALKTIME: '',
    TIME: '',
    REASON: '',
    //urine
    UURINE: '',
    //sleep
    NAP: '',
    NNAP: '',
    TIMENAP: '',
    TIRED: ''
  }),

  methods: {
    adddm: function(event) {
      var data = {
        DATE: this.DATE,
        EAT: this.EAT,
        FBS: this.FBS
      }
      axios.post('https://foregoing-precious-spoon.glitch.me//insertDM', data).then(response => {
        // this.info = response.data[3]
        console.log(response)
      })
    },
    addht: function(event) {
      var data = {
        DATE: this.DATE,
        SBP: this.SBP,
        DBP: this.DBP
      }
      axios.post('http://localhost:3000/insertHT', data).then(response => {
        // this.info = response.data[3]
        console.log(response)
      })
    },
    add2q: function(event) {
      var data = {
        DATE: this.DATE,
        DISMAL: this.DISMAL,
        BORED: this.BORED
      }
      axios.post('http://localhost:3000/insert2Q', data).then(response => {
        // this.info = response.data[3]
        console.log(response)
      })
    },
    addoral: function(event) {
      var data = {
        DATE: this.DATE,
        LIPS: this.LIPS,
        GUMS: this.GUMS,
        TEETH: this.TEETH,
        CHEW: this.CHEW,
        ARTIFICIALTEETH: this.ARTIFICIALTEETH
      }
      axios.post('http://localhost:3000/insertORAL', data).then(response => {
        // this.info = response.data[3]
        console.log(response)
      })
    },
    addnutritional: function(event) {
      var data = {
        DATE: this.DATE,
        BMI: this.BMI,
        WAIGHT: this.WAIGHT,
        HIGH: this.HIGH
      }
      axios
        .post('http://localhost:3000/insertNUTRITIONAL', data)
        .then(response => {
          // this.info = response.data[3]
          console.log(response)
        })
    },
    addeye: function(event) {
      var data = {
        DATE: this.DATE,
        INCHCOUNT: this.INCHCOUNT,
        READ: this.READ,
        AMBLYOPIA: this.AMBLYOPIA,
        CLEARLYSEE: this.CLEARLYSEE,
        SPOTS: this.SPOTS
      }
      axios.post('http://localhost:3000/insertEYE', data).then(response => {
        // this.info = response.data[3]
        console.log(response)
      })
    },
    addadl: function(event) {
      var data = {
        DATE: this.DATE,
        EATING: this.EATING,
        FACE: this.FACE,
        USETOILET: this.USETOILET,
        BATHE: this.BATHE,
        GARB: this.GARB,
        GETUG: this.GETUG,
        MOVE: this.MOVE,
        DOWNSTAIRS: this.DOWNSTAIRS,
        WFECES: this.WFECES,
        WURINE: this.WURINE,
      }
      axios.post('http://localhost:3000/insertADL', data).then(response => {
        // this.info = response.data[3]
        console.log(response)
      })
    },
    addosteoarthritis: function(event) {
      var data = {
        DATE: this.DATE,
        KNEEPAIN: this.KNEEPAIN
      }
      axios.post('http://localhost:3000/insertOSTEOARTHRITIS', data).then(response => {
        // this.info = response.data[3]
        console.log(response)
      })
    },
    addtugt: function(event) {
      var data = {
        DATE: this.DATE,
        WALKTIME: this.WALKTIME,
        TIME: this.TIME,
        REASON: this.REASON
      }
      axios.post('http://localhost:3000/insertTUGT', data).then(response => {
        // this.info = response.data[3]
        console.log(response)
      })
    },
    addurine: function(event) {
      var data = {
        DATE: this.DATE,
        UURINE: this.UURINE
      }
      axios.post('http://localhost:3000/insertURINE', data).then(response => {
        // this.info = response.data[3]
        console.log(response)
      })
    },
    addsleep: function(event) {
      var data = {
        DATE: this.DATE,
        NAP: this.NAP,
        NNAP: this.NNAP,
        TIMENAP: this.TIMENAP,
        TIRED: this.TIRED,
      }
      axios.post('http://localhost:3000/insertSLEEP', data).then(response => {
        // this.info = response.data[3]
        console.log(response)
      })
    },
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>

