<template>
  <NavBar />
  <div class="flex items-start">
    <!-- Side -->
    <SideBar />
    <!-- Main -->
    <div class="px-20 py-10">
      <div class="flex items-center">
        <img src="../assets/svg/ppl.svg" alt="" class="ml-5" />
        <h1 class="text-2xl font-bold text-sky-700">المواطنين</h1>
      </div>
      <div class="flex items-center justify-evenly mt-5">
        <!-- last update -->
        <div>
          <h1>اخر تحديث</h1>
          <div
            class="bg-white mx-4 shadow-lg shadow-gray-300 border border-gray-300 h-32 w-56 rounded-xl items-start px-5 space-y-3 flex flex-col justify-center mt-2"
          >
            <div class="flex items-center justify-between">
              <img src="../assets/svg/calender.svg" alt="" class="ml-5" />
              <h1>{{ dateNow }}</h1>
            </div>
            <div class="flex items-center justify-between">
              <img src="../assets/svg/clock.svg" alt="" class="ml-5" />
              <h1>{{ timeNow }}</h1>
            </div>
            <div class="flex items-center justify-between">
              <img src="../assets/svg/pp.svg" alt="" class="ml-5" />
              <h1>{{ username }}</h1>
            </div>
          </div>
        </div>
        <!-- created -->
        <div>
          <h1>تاريخ الانشاء</h1>
          <div
            class="bg-white mx-4 shadow-lg shadow-gray-300 border border-gray-300 h-32 w-56 rounded-xl items-start px-5 space-y-3 flex flex-col justify-center mt-2"
          >
            <div class="flex items-center justify-between">
              <img src="../assets/svg/calender.svg" alt="" class="ml-5" />
              <h1>{{ dateNow }}</h1>
            </div>
            <div class="flex items-center justify-between">
              <img src="../assets/svg/clock.svg" alt="" class="ml-5" />
              <h1>{{ timeNow }}</h1>
            </div>
            <div class="flex items-center justify-between">
              <img src="../assets/svg/pp.svg" alt="" class="ml-5" />
              <h1>{{ username }}</h1>
            </div>
          </div>
        </div>
        <!-- status -->
        <div>
          <h1>الحالة</h1>
          <div
            class="bg-white mx-4 shadow-lg shadow-gray-300 border border-gray-300 h-32 w-56 rounded-xl items-center px-5 space-y-3 flex flex-col justify-center mt-2"
          >
            <h1 class="text-green-600 text-xl">{{ status }}</h1>
          </div>
        </div>
        <!-- number -->
        <div>
          <h1>رقم المواطن</h1>
          <div
            class="bg-white mx-4 shadow-lg shadow-gray-300 border border-gray-300 h-32 w-56 rounded-xl items-center px-5 space-y-3 flex flex-col justify-center mt-2"
          >
            <h1 class="text-xl">{{ ppNumber }}</h1>
          </div>
        </div>
      </div>
      <!-- Form -->
      <div class="mt-10 flex justify-evenly items-center">
        <!-- left -->
        <div class="flex flex-col items-start justify-evenly space-y-4">
          <h1>الاسم</h1>
          <input
            v-model="name"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>اسم الاب</h1>
          <input
            v-model="fatherName"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>اسم الجد</h1>
          <input
            v-model="middleName"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>اللقب</h1>
          <input
            v-model="lastName"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>اسم الام</h1>
          <input
            v-model="motherName"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>تاريخ الميلاد</h1>
          <input
            v-model="birthDay"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="date"
          />
          <h1>محل الولادة</h1>
          <input
            v-model="birthLoc"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>الجنس</h1>
          <select
            v-model="gender"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
          >
            <option value=""></option>
            <option value="ذكر">ذكر</option>
            <option value="انثى">انثى</option>
          </select>
          <h1>الحالة</h1>
          <select
            v-model="statusOfReal"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
          >
            <option value=""></option>
            <option value="متزوح">متزوج</option>
            <option value="اعزب">اعزب</option>
          </select>
          <h1>اسم الزوج / الزوجة</h1>
          <input
            v-model="nameOfHOrW"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
        </div>
        <!-- Right -->
        <div class="flex flex-col items-start justify-evenly space-y-4">
          <h1>العنوان الاول</h1>
          <input
            v-model="addressOne"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>العنوان الثاني</h1>
          <input
            v-model="addressTwo"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>المدينة</h1>
          <input
            v-model="city"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>المحافظة</h1>
          <input
            v-model="city2"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>ZIP CODE</h1>
          <input
            v-model="zipCode"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>الدولة</h1>
          <input
            v-model="country"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>رقم الهاتف</h1>
          <input
            v-model="phoneNumber"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="number"
          />
          <h1>البريد الالكتروني</h1>
          <input
            v-model="email"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>اسم الوكيل</h1>
          <input
            v-model="nameOfPer"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
            type="text"
          />
          <h1>متوفي</h1>
          <select
            v-model="dieOrNot"
            class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
          >
            <option value=""></option>
            <option value="نعم">نعم</option>
            <option value="كلا">كلا</option>
          </select>
        </div>
      </div>
      <div class="mt-10 mx-32 flex flex-col items-start justify-start">
        <h1>يرجي اختيار نوع المعاملة من الحقل ادناه</h1>
        <select
          v-model="dieOrNot"
          class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
        >
          <option value=""></option>
          <option value="وكالة عامة">وكالة عامة</option>
          <option value="وكالة عقارية">وكالة عقارية</option>
        </select>
      </div>

      <div class="flex items-end justify-end mt-20">
        <button
          v-on:click="saveToLocal"
          class="bg-sky-600 px-14 py-5 rounded-xl text-white flex items-center justify-center"
        >
          انشاء
          <img src="../assets/svg/go.svg" alt="" class="w-7 mr-3" />
        </button>
      </div>
    </div>
  </div>
</template>
<script>
import NavBar from "../components/NavBar.vue";
import SideBar from "../components/Sidebar.vue";
export default {
  name: "HomePage",
  components: { NavBar, SideBar },
  data() {
    return {
      dateNow: this.getDateNow()[0],
      timeNow: this.getDateNow()[1],
      username: "user.user",
      status: "Active",
      ppNumber: this.createPpNumber(),
      // Form Data
      name: "",
      fatherName: "",
      middleName: "",
      lastName: "",
      motherName: "",
      birthDay: "",
      birthLoc: "",
      gender: "",
      statusOfReal: "",
      nameOfHOrW: "",
      addressOne: "",
      addressTwo: "",
      city: "",
      city2: "",
      zipCode: "",
      country: "",
      phoneNumber: "",
      email: "",
      nameOfPer: "",
      dieOrNot: "",
      formLocal: this.getData(),
    };
  },
  created() {
    // setInterval(this.getDateNow);
    // setInterval(this.createPpNumber, 1000);
  },
  methods: {
    getDateNow() {
      const today = new Date();
      const date =
        today.getDay() + "/" + today.getMonth() + "/" + today.getFullYear();

      const time =
        today.getHours() + ":" + today.getMinutes() + ":" + today.getSeconds();
      // this.dateNow = date;
      // this.timeNow = time;
      return [date, time];
    },
    createPpNumber() {
      const date = new Date();
      const today = date.getFullYear() + date.getMonth() + date.getDay();
      const min = 1000000;
      const max = 9999999;
      const ppNum = today + Math.floor(Math.random() * (max - min + 1) - min);
      return ppNum;
    },
    saveToLocal() {
      const formData = {
        name: this.name,
        fatherName: this.fatherName,
        middleName: this.middleName,
        lastName: this.lastName,
        motherName: this.motherName,
        birthDay: this.birthDay,
        birthLoc: this.birthLoc,
        gender: this.gender,
        statusOfReal: this.statusOfReal,
        nameOfHOrW: this.nameOfHOrW,
        addressOne: this.addressOne,
        addressTwo: this.addressTwo,
        city: this.city,
        city2: this.city2,
        zipCode: this.zipCode,
        country: this.country,
        phoneNumber: this.phoneNumber,
        email: this.email,
        nameOfPer: this.nameOfPer,
        dieOrNot: this.dieOrNot,
        timeCreated: this.timeNow,
        dateCreated: this.dateNow,
        status: this.status,
        ppNumber: this.ppNumber,
      };
      console.log(formData);
      localStorage.setItem("formData", JSON.stringify(formData));
      console.log(JSON.parse(localStorage.getItem("formData")));
      // return this.$router.push({ name: "HomePage" });
    },
    getData() {
      const formDate1 = JSON.parse(localStorage.getItem("formData"));
      return formDate1;
    },
    consoleLogOne() {
      console.log(this.formLocal.addressOne);
    },
  },
};
</script>
