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
          خطوة رقم 2 - انشاء
        </h1>
        <div
          class="w-[63rem] bg-white shadow-lg shadow-gray-400 h-[28rem] rounded-xl border border-gray-300 flex flex-col items-center p-10"
        >
          <h1>وكالة عامة مخصوصةعقارية(بيع عقار)</h1>
          <h1>رقم الصادر:</h1>
          <p class="text-md leading-relaxed mt-5">
            اني الموقع ادناه {{ form.nameOfOne }} قد وكلت السيد
            {{ form.nameOfTwo }}
            وكالة عامة عقارية مخصوصة و قد خولته ان يمارس كافة الحقوق الممنوحة لي
            شرعاً و عرفاً فيما يتعلق بالقطعة المرقمة
            {{ form.numOfProperty }} رقم المقاطعة {{ form.numOfSide }} اسم
            القطعة {{ form.paperOfIdentityOfOne }} المحافظة{{ form.nameOfCity }}
            و مراجعة كافة الدوائر الرسمية و شبه الرسمية منها أمانة بغداد او
            الدوائر البلدية المختصة و فروعها و اعطاء كافة التعهدات المطلوبة و
            الحصول على اجازة البناء و مراجعة الشركة العامة للمواد الانشائية و
            استلام المواد الانشائية كافة و المواد الصحية و الطابوق و مراجعة
            الشركة العامة للأسمنت العراقية و استلام المواد كافة و مراجعة ضريبة
            الدخل و ضريبة العقار و التمتع بالاعفاء المطلق او الجزئي او دفع رسوم
            المقتضية لذلك و مراجعة مديرية التسجيل العقاري المختص لتقريرها نيابة
            عني و مراجعة المحاكم و الدوائر التنفيذ و الاعتراض او القبول لكافة
            قرارتها ووضع الحجز التنفيذي او الاحتياطي و خولته البيع و بالسعر الي
            يراه مناسباً و الشراء و القبض و الرهن و الايجار و الاستئجار كما
            خولته اعطاء التعهدات الى ضريبة العرصات لهذا العقار و خولته طلب
            العدول و الابطال و اضافة اسم المشتري و فتح بيان و مرافقة لجان الكشف
            و خولته حق توكيل الغير بكل او ببعض ما وكل به وكالة عامة مفوضة لرايه،
            ولاجله وقعت **
          </p>
        </div>
        <div class="flex justify-end mt-10">
          <button
            v-on:click="savaAndCount"
            class="bg-sky-600 flex justify-center items-center text-white text-md px-10 py-5 rounded-xl hover:bg-sky-700"
          >
            متابعة
            <img src="../assets/svg/go.svg" alt="" class="w-7 mr-2" />
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
  name: "CreatedForm2",
  components: { SideBar, NavBar },
  data() {
    return {
      form: "",
      template: "",
    };
  },
  created() {
    setInterval(this.getData(), 10000);
  },
  methods: {
    getData() {
      const Data = JSON.parse(localStorage.getItem("CreatedForm"));
      this.form = Data;
      console.log(this.form);
    },
    savaAndCount() {
      this.$router.push({ name: "DownloadPage" });
    },
  },
};
</script>
