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
        <h1 class="my-10 text-2xl font-light text-sky-600">خطوة رقم 3 - حفظ</h1>
        <div
          class="w-[63rem] bg-white shadow-lg shadow-gray-400 h-[28rem] rounded-xl border border-gray-300 flex justify-around items-center p-10"
        >
          <div>
            <h1 class="text-2xl">وكالة عامة مخصوصة عقارية(بيع عقار)</h1>
            <p class="text-xl">سوف يبدء التحميل خلال ٥ ثواني</p>
          </div>
          <a
            href="../assets/svg/A4 - 1.jpg"
            download="file.pdf"
            target="_blank"
          >
            <img src="../assets/svg/check.svg" alt="" />
          </a>
        </div>
        <div class="flex justify-end mt-10">
          <button
            v-on:click="savaAndCount"
            class="bg-red-600 flex justify-center items-center text-white text-md px-10 py-5 rounded-xl hover:bg-sky-700"
          >
            ارسال
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
  name: "DownloadPage",
  components: { SideBar, NavBar },
  data() {
    return {
      item: { loc: require("../assets/svg/A4 - 1.jpg") },
    };
  },
  created() {
    // setInterval(this.download(), 50000);
  },
  methods: {
    // download() {
    //   const link = document.createElement("a");
    //   link.href = "../../public/A4 - 1.pdf";
    //   link.setAttribute("download", "file.pdf");
    //   link.click();
    // },
  },
};
</script>
