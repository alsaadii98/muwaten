<template>
  <div>
    <!-- Nav -->
    <NavBar />
    <div class="flex items-start">
      <!-- Side -->
      <SideBar />
      <!-- Main -->
      <div class="px-20 py-10">
        <div class="flex items-center">
          <img src="../assets/svg/form.svg" alt="" class="ml-5" />
          <h1 class="text-2xl font-bold text-sky-700">طلب توثيق</h1>
        </div>

        <div class="flex items-center justify-evenly mt-5">
          <!-- last update -->
          <div>
            <h1>رقم المواطن</h1>
            <div
              class="bg-white mx-4 shadow-lg shadow-gray-300 border border-gray-300 h-32 w-56 rounded-xl items-center px-5 space-y-3 flex flex-col justify-center mt-2"
            >
              <h1 class="text-xl">12345678</h1>
            </div>
          </div>
          <!-- created -->
          <div>
            <h1>البعثة</h1>
            <div
              class="bg-white mx-4 shadow-lg shadow-gray-300 border border-gray-300 h-32 w-56 rounded-xl items-center px-5 space-y-3 flex flex-col justify-center mt-2"
            >
              <h1 class="text-xl">بغداد</h1>
            </div>
          </div>
          <!-- status -->
          <div>
            <h1>القسم</h1>
            <div
              class="bg-white mx-4 shadow-lg shadow-gray-300 border border-gray-300 h-32 w-56 rounded-xl items-center px-5 space-y-3 flex flex-col justify-center mt-2"
            >
              <h1 class="text-xl">الوكلات العامة</h1>
            </div>
          </div>
          <!-- number -->
          <div>
            <h1>رقم الوثيقة</h1>
            <div
              class="bg-white mx-4 shadow-lg shadow-gray-300 border border-gray-300 h-32 w-56 rounded-xl items-center px-5 space-y-3 flex flex-col justify-center mt-2"
            >
              <h1 class="text-xl text-green-500">12345678</h1>
            </div>
          </div>
        </div>
        <h1 class="my-10 text-2xl font-light text-sky-600">
          خطوة رقم 1- ادخال المعلومات
        </h1>
        <div class="mt-10 flex justify-evenly items-center">
          <!-- left -->
          <div class="flex flex-col items-start justify-evenly space-y-4">
            <h1>اسم الموكل</h1>
            <input
              v-model="nameOfOne"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="text"
            />
            <h1>رقم العقار</h1>
            <input
              v-model="numOfProperty"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="text"
            />
            <h1>اسم المحافظة</h1>
            <input
              v-model="nameOfCity"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="text"
            />
            <h1>عنوان الموكل</h1>
            <input
              v-model="addressOfOne"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="text"
            />
            <h1>جواز سفر الموكل</h1>
            <input
              v-model="passportOfOne"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="text"
            />
            <h1>تاريخ اصدار جواز سفر الموكل</h1>
            <input
              v-model="passportDataOfOne"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="date"
            />
            <h1>تاريخ صدور هوية الاحول للموكل</h1>
            <input
              v-model="identityDateOfOne"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="date"
            />
            <h1>صحيفة هوية الاحوال للموكل</h1>
            <input
              v-model="paperOfIdentityOfOne"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="text"
            />
          </div>
          <!-- Right -->
          <div class="flex flex-col items-start justify-evenly space-y-4">
            <h1>اسم الوكيل</h1>
            <input
              v-model="nameOfTwo"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="text"
            />
            <h1>رقم المقاطعة</h1>
            <input
              v-model="numOfProperty"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="text"
            />
            <h1>رقم الوصل</h1>
            <input
              v-model="numOfRecite"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="text"
            />
            <h1>هاتف الموكل</h1>
            <input
              v-model="phoneNumber"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="text"
            />
            <h1>مكان الاصدار جواز سفر الموكل</h1>
            <input
              v-model="passportLoc"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="text"
            />
            <h1>هوية الاحول للموكل</h1>
            <input
              v-model="identityOfOne"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="text"
            />
            <h1>سجل هوية الاحوال للموكل</h1>
            <input
              v-model="recodeOfOne"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="number"
            />
            <h1>شهادة الجنسية للموكل</h1>
            <input
              v-model="shadedOfOne"
              class="w-80 bg-white border border-gray-300 py-4 px-2 rounded-xl"
              type="text"
            />
          </div>
        </div>
        <div class="flex items-end justify-end mt-20">
          <button
            v-on:click="setData"
            class="bg-sky-600 px-14 py-5 rounded-xl text-white flex items-center justify-center"
          >
            انشاء
            <img src="../assets/svg/go.svg" alt="" class="w-7 mr-3" />
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import SideBar from "@/components/Sidebar.vue";
import NavBar from "@/components/NavBar.vue";
export default {
  name: "CreateForm",
  components: { SideBar, NavBar },
  data() {
    return {
      nameOfOne: "",
      nameOfTwo: "",
      numOfProperty: "",
      numOfSide: "",
      nameOfCity: "",
      numOfRecite: "",
      addressOfOne: "",
      phoneNumber: "",
      passportOfOne: "",
      passportLoc: "",
      passportDataOfOne: "",
      identityOfOne: "",
      identityDateOfOne: "",
      recodeOfOne: "",
      paperOfIdentityOfOne: "",
      shadedOfOne: "",
    };
  },
  methods: {
    setData() {
      const CreatedForm = {
        nameOfOne: this.nameOfOne,
        nameOfTwo: this.nameOfTwo,
        numOfProperty: this.numOfProperty,
        numOfSide: this.numOfSide,
        nameOfCity: this.nameOfCity,
        numOfRecite: this.numOfRecite,
        addressOfOne: this.addressOfOne,
        phoneNumber: this.phoneNumber,
        passportOfOne: this.passportOfOne,
        passportLoc: this.passportLoc,
        passportDataOfOne: this.passportDataOfOne,
        identityOfOne: this.identityOfOne,
        identityDateOfOne: this.identityDateOfOne,
        recodeOfOne: this.recodeOfOne,
        paperOfIdentityOfOne: this.paperOfIdentityOfOne,
        shadedOfOne: this.shadedOfOne,
      };
      localStorage.setItem("CreatedForm", JSON.stringify(CreatedForm));
      //   console.log(JSON.parse(localStorage.getItem("CreatedForm")));
      this.$router.push({ name: "CreateForm2" });
    },
  },
};
</script>
