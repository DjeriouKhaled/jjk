<template>

  <div class="bg-gradient-to-br from-pink-100 via-white to-blue-100 min-h-screen flex items-center justify-center">
    
 
  <div class=" container  mx-auto px-4 font-sans">
    <!-- Header -->
    <header class="flex  items-center justify-between  w-full  p-2">
    <!-- Content for larger screens -->
    <div class="hidden lg:flex   items-start space-x-4">
      <span class="font-semibold text-blue-950">khaledjr2018@gmail.com</span>
      <button  @click.prevent="copyText"  class="bg-slate-50 text-gray-600 hover:text-gray-900 rounded-full p-1 px-2 text-sm flex items-center space-x-2">
        <!-- <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 14" id="Gmail--Streamline-Core" height="20" width="20"><desc>Gmail Icon</desc><g id="gmail"><path id="Union" fill="#8fbffa" fill-rule="evenodd" d="M1.00772 12.0542h2.76535V7.68637l3.26988 2.11682 3.26995 -2.11683v4.36784h2.7653c0.5091 0 0.9218 -0.4112 0.9218 -0.9185V3.75445c0 -1.45329 -1.6136 -2.33103 -2.8405 -1.54516l-0.8466 0.54231v0.00119L7.04295 4.85187 3.77307 2.75279V2.7516l-0.84665 -0.54231C1.69951 1.42342 0.0859375 2.30116 0.0859375 3.75445v7.38125c0 0.5073 0.4126965 0.9185 0.9217825 0.9185Z" clip-rule="evenodd" stroke-width="1"></path><path id="Intersect" fill="#2859c5" fill-rule="evenodd" d="M3.77307 7.68637 0.0859375 5.29944V3.75445c0 -1.45329 1.6135725 -2.33103 2.8404825 -1.54516l0.84665 0.5435v4.93358ZM14 5.29944V3.75445c0 -1.45329 -1.6136 -2.33103 -2.8405 -1.54516l-0.8466 0.5435v4.93357L14 5.29944Z" clip-rule="evenodd" stroke-width="1"></path></g></svg> -->
        <!-- <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 14" id="Gmail--Streamline-Core" height="22" width="22"><desc>Gmail Streamline Icon: https://streamlinehq.com</desc><g id="gmail"><path id="Rectangle 18" stroke="#172554" stroke-linecap="round" stroke-linejoin="round" d="M1.74275 12.0032h2.65011V3.0883l-0.81137 -0.51971C2.40571 1.81546 0.859375 2.65663 0.859375 4.04936V11.123c0 0.4861 0.395495 0.8802 0.883375 0.8802Z" stroke-width="1"></path><path id="Rectangle 20" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" d="M0.859375 4.04936v1.1765L4.39286 7.48917l2.65011 1.69748 2.65011 -1.69748 3.53352 -2.26331v-1.1765c0 -1.39273 -1.5464 -2.2339 -2.7222 -1.48077l-0.81132 0.51971 -2.65011 1.69748L4.39286 3.0883l-0.81137 -0.51971C2.40571 1.81546 0.859375 2.65663 0.859375 4.04936Z" stroke-width="1"></path><path id="Rectangle 19" stroke="#000000" stroke-linecap="round" stroke-linejoin="round" d="M9.69305 12.0032h2.65015c0.4878 0 0.8833 -0.3941 0.8833 -0.8802V4.04936c0 -1.39273 -1.5463 -2.2339 -2.7221 -1.48077l-0.81135 0.51971v8.9149Z" stroke-width="1"></path></g></svg> -->
        <span>copy</span>
      </button>

       <!-- Toast component -->
          <!-- Toast Component -->
    
    <!-- <Toast ref="toast" message="Text copied to clipboard!" /> -->
      <!-- <a href="#" class="bg-gray-100 text-gray-600 hover:text-gray-900 rounded-full p-1 px-4 text-sm flex items-center space-x-2">
         <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
           <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7v10M16 7v10M12 7v10M20 12H4" />
         </svg>
         <span>Copy</span>
      </a> -->
      <a href="https://aqua-kaile-5.tiiny.site" class="bg-slate-50 text-gray-600 hover:text-gray-900 rounded-full p-1 px-4 text-sm">cv</a>
     
    </div>
    <Toast :message="toastMessage" :visible="isToastVisible" />
    <Toast :message="toastMessage2" :visible="isToastVisible2" />
   <!-- Dynamic links for larger screens -->
   <!-- Dynamic links for larger screens -->
   <div class="hidden lg:flex items-center flex-grow justify-end"> <!-- Updated flex settings -->
    <div class="flex space-x-6"> <!-- Flex for the links -->
      <a v-for="link in links" :key="link.url" :href="link.url" class="text-gray-600 hover:text-blue-500 transition duration-300 text-sm font-semibold rounded-md p-2">
        {{ link.text }}
      </a>
    </div>
  </div>

    <!-- Content for smaller screens -->
    <div class="lg:hidden flex items-center justify-between w-full px-4">
  <img src="@/assets/jk.svg" alt="Logo" class="w-12 h-12 md:w-12 lg:w-" /> <!-- JK Logo -->
  
  <button
    type="button"
    class="mobile-nav-toggle"
    aria-label="mobile-menu"
    @click="toggleMenu"
  >
    <img src="@/assets/menu-line.svg" alt="Menu" class="w-6 h-6 p-1" />
  </button>
</div>


    <!-- Navigation overlay for smaller screens -->
    <div @click="toggleMenu" class="relative">
    <div @click="handleOverlayClick" v-if="isMenuOpen" class="fixed inset-0 bg-gray-800 bg-opacity-75 z-50 flex flex-col items-center justify-center" >
     
      <div @click="toggleMenu" class="bg-white rounded-xl shadow-lg p-6 w-80">
        <button @click="toggleMenu" class="absolute top-4 right-4 p-0 text-gray-100 hover:text-gray-200">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                </svg>
            </button>
      <div class="flex items-center justify-between mb-4">
        <div class="flex items-center space-x-1">

          <a href="https://aqua-kaile-5.tiiny.site" >
          <svg  class="w-5 h-5 text-gray-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"></path>
          </svg>
        </a>
          <button class="text-gray-600 hover:text-gray-800">
            <a href="https://aqua-kaile-5.tiiny.site" class="font-semibold text-gray-800">CV</a>
          </button>
         
        </div>
        <div  class="flex items-center space-x-1 text-sm  text-gray-600" >
          <span >khaledjr2018@gmail.com</span>
          <button class="text-gray-600 hover:text-gray-800" @click="copyTextInMenu()">
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <rect x="9" y="9" width="13" height="13" rx="2" ry="2" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></rect>
              <path d="M5 15H4a2 2 0 01-2-2V4a2 2 0 012-2h9a2 2 0 012 2v1" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path>
            </svg>

          </button>
        </div>
      </div>

      <div class="space-y-2">
        <!-- facebook -->
    
          <a href="https://www.facebook.com/profile.php?id=61550237961572" @click="toggleMenu"  class="w-full flex items-center justify-between hover:bg-gray-100 rounded-lg px-4 py-2 text-left">
          <div class="flex items-center space-x-2">
        
          
          <svg class="w-5 h-5" xmlns="http://www.w3.org/2000/svg" fill="#1877F2"  viewBox="7.025 7.025 497.951 497.95">
            <path d="M480,257.35c0-123.7-100.3-224-224-224s-224,100.3-224,224c0,111.8,81.9,204.47,189,221.29V322.12H164.11V257.35H221V208c0-56.13,33.45-87.16,84.61-87.16,24.51,0,50.15,4.38,50.15,4.38v55.13H327.5c-27.81,0-36.51,17.26-36.51,35v42h62.12l-9.92,64.77H291V478.66C398.1,461.85,480,369.18,480,257.35Z" fill-rule="evenodd"/>
          </svg>
            <span>فيسبوك</span>
          </div>
        </a>
          <!-- <span class="text-xs text-gray-500">⌘R</span> -->
        

        <a href="https://www.linkedin.com/in/jirou-khalid/" @click="toggleMenu" class="w-full flex items-center space-x-2 hover:bg-gray-100 rounded-lg px-4 py-2 text-left">
          <svg class="w-5 h-5" xmlns="http://www.w3.org/2000/svg" viewBox="7.025 7.025 497.951 497.95">
            <linearGradient id="a" gradientUnits="userSpaceOnUse" x1="-974.482" y1="1306.773" x2="-622.378" y2="1658.877" gradientTransform="translate(1054.43 -1226.825)">
              <stop offset="0" stop-color="#2489be"/>
              <stop offset="1" stop-color="#0575b3"/>
            </linearGradient>
            <path d="M256 7.025C118.494 7.025 7.025 118.494 7.025 256S118.494 504.975 256 504.975 504.976 393.506 504.976 256C504.975 118.494 393.504 7.025 256 7.025zm-66.427 369.343h-54.665V199.761h54.665v176.607zM161.98 176.633c-17.853 0-32.326-14.591-32.326-32.587 0-17.998 14.475-32.588 32.326-32.588s32.324 14.59 32.324 32.588c.001 17.997-14.472 32.587-32.324 32.587zm232.45 199.735h-54.4v-92.704c0-25.426-9.658-39.619-29.763-39.619-21.881 0-33.312 14.782-33.312 39.619v92.704h-52.43V199.761h52.43v23.786s15.771-29.173 53.219-29.173c37.449 0 64.257 22.866 64.257 70.169l-.001 111.825z" fill="url(#a)"/>
          </svg>


              <span>لينكد إن </span>
        </a>
            <a href="https://t.me/khaled_djeriou" @click="toggleMenu" class="w-full flex items-center space-x-2 hover:bg-gray-100 rounded-lg px-4 py-2 text-left">
              <svg class="w-5 h-5 text-gray-600" xmlns="http://www.w3.org/2000/svg" fill="none" height="2500" width="2500" viewBox="0 0 500 500">
                <path d="M250 500c138.071 0 250-111.929 250-250S388.071 0 250 0 0 111.929 0 250s111.929 250 250 250z" fill="#34aadf"/>
                <path d="M104.047 247.832s125-51.3 168.352-69.364c16.619-7.225 72.977-30.347 72.977-30.347s26.012-10.115 23.844 14.451c-.723 10.116-6.503 45.52-12.283 83.815-8.671 54.191-18.064 113.439-18.064 113.439s-1.445 16.619-13.728 19.509-32.515-10.115-36.127-13.006c-2.891-2.167-54.191-34.682-72.977-50.578-5.058-4.335-10.838-13.005.722-23.121 26.012-23.844 57.081-53.468 75.867-72.254 8.671-8.671 17.341-28.902-18.786-4.336-51.3 35.405-101.878 68.642-101.878 68.642s-11.561 7.225-33.237.722c-21.677-6.502-46.966-15.173-46.966-15.173s-17.34-10.838 12.284-22.399z" fill="#fff"/>
              </svg>

              <span>تلغرام</span>
            </a>
        <!-- <button class="w-full flex items-center justify-between hover:bg-gray-100 rounded-lg px-4 py-2 text-left">
          <div class="flex items-center space-x-2">
            <svg class="w-5 h-5 text-gray-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path>
            </svg>
            <span>Search</span>
          </div>
          <span class="text-xs text-gray-500">⌘S</span>
        </button> -->

       
      </div>
    </div>
      <!--

      <nav class="flex flex-col space-y-4 text-white text-lg transition duration-300 transform ease-in-out origin-top"
        :class="{'scale-y-100 opacity-100': isMenuOpen, 'scale-y-0 opacity-0': !isMenuOpen}">
        <a href="#" @click="toggleMenu">khaledjr2018@gmail.com</a>
        <a href="#" @click="toggleMenu">CV</a>
        <a href="#" @click="toggleMenu">لينكدان</a>
        <a href="#" @click="toggleMenu">دريبل</a>
        <a href="#" @click="toggleMenu">انستقرام</a>
      </nav> -->
    </div>
  </div>

  </header>


    <!-- Hero Section -->
    <section class="text-center py-16">
      <div class="relative inline-block mb-12">
        <img src="./assets/placeholder-profile.png" alt="Profile" class="w-40 h-40 rounded-full mb-8">
        <span class="absolute bottom-0 right-0 font-sans font-semibold font-cairo  text-xl lg:text-2xl px-0 py-0 rounded-full text-center w-full  text-slate-900">جريو خالد</span>
      </div>
      <h1 class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl font-cairo text-slate-900 font-normal mb-5">نحو انطلاقة رقمية مثالية 
        تصميم وتطوير مواقع وتطبيقات بجودة عالية  </h1>
      <button @click="latestWork"  class="bg-slate-900 text-white px-6 py-2 rounded-full">اخر اعمالي</button>
    </section>

    <!-- Clients Section -->
    <section class="py-8">
      <div class="flex flex-wrap justify-center items-center gap-8">
        <img src="./assets/adobe.png" alt="Adobe" class="h-10 grayscale">
        <img src="./assets/java-script.webp" alt="Adobe" class="h-8 grayscale">
        <img src="./assets/Figma-Logo.png" alt="figma" class="h-10 grayscale">
        <img src="./assets/press.png" alt="wordpress" class="h-10 grayscale">
        <img src="./assets/f.png" alt="flutter" class="h-16 grayscale">
      </div>
    </section>

    <!-- Services Section -->
    <section class="py-16">
      <h2 class="text-2xl font-bold text-center text-slate-900 mb-12">خدمات أقدمها </h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
        <div class="text-center">
          <div class="mb-4 ">
            <svg class="w-10 h-10 mx-auto" fill="none" stroke="#1f2937" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path></svg>
          </div>
          <h3 class="font-semibold mb-2 text-slate-900">UX & UI</h3>
          <p class="text-sm text-gray-600">تصميم واجهات سهلة الاستخدام وفعالة وممتعة للاستخدام.</p>
        </div>
        <div class="text-center">
          <div class="mb-4">
            <svg class="w-10 h-10 mx-auto" fill="none" stroke="#1f2937" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z"></path></svg>
          </div>
          <h3 class="font-semibold mb-2 text-slate-900">Web & Mobile App</h3>
          <p class="text-sm text-gray-600">تحويل الأفكار إلى تجارب استثنائية لتطبيقات الويب والهواتف المحمولة.</p>
        </div>
        <div class="text-center">
          <div class="mb-4">
            <svg class="w-10 h-10 mx-auto text-slate-900" fill="none" stroke="#1f2937" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z"></path></svg>
          </div>
          <h3 class="font-semibold mb-2">Design & Creative</h3>
          <p class="text-sm text-gray-600">إنشاء تصميمات مذهلة بصريًا تتواصل مع جمهورك.</p>
        </div>
        <div class="text-center">
          <div class="mb-4">
            <svg class="w-10 h-10 mx-auto " fill="none" stroke="#1f2937" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"></path></svg>
          </div>
          <h3 class="font-semibold mb-2 text-slate-900">Development</h3>
          <p class="text-sm text-gray-600">جلب رؤيتك إلى الحياة مع أحدث التقنيات واتجاهات التصميم.</p>
        </div>
      </div>
    </section>

    <!-- Call to Action Section -->
    <section class="text-center py-16">
      <div class="mb-8">
        <svg class="w-14 h-14 mx-auto" fill="none" stroke="#0f172a" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 10h4.764a2 2 0 011.789 2.894l-3.5 7A2 2 0 0115.263 21h-4.017c-.163 0-.326-.02-.485-.06L7 20m7-10V5a2 2 0 00-2-2h-.095c-.5 0-.905.405-.905.905 0 .714-.211 1.412-.608 2.006L7 11v9m7-10h-2M7 20H5a2 2 0 01-2-2v-6a2 2 0 012-2h2.5"></path></svg>
      </div>
      <h2 class="text-2xl font-bold mb-8 text-slate-900">أخبرني عن مشروعك القادم</h2>
      <div class="mt-4 flex justify-center items-center space-x-2">
        <a href="https://t.me/khaled_djeriou" class="bg-gray-50 text-slate-900 border border-slate-900 px-6 py-2 rounded-full">تلغرام</a>
     
        <a
  :href="`https://mail.google.com/mail/?view=cm&fs=1&to=khaledjr2018@gmail.com&su=${encodeURIComponent('Subject')}&body=${encodeURIComponent('Your Message')}`"
  class="bg-slate-900 text-white px-6 py-2 rounded-full"
  target="_blank"
  >أرسل لي بريدا إلكترونيا</a>

     </div>
    </section>

    <!-- Footer -->
    <footer class="py-8 text-center text-sm text-gray-600">
      <p>© 2024 جميع الحقوق محفوظة.</p>
      <div class="mt-4 flex justify-center items-center space-x-2">
        <div class="flex space-x-6">
          <a v-for="link in links" :key="link.url" :href="link.url" class="text-gray-600 hover:text-blue-500 transition duration-300 text-sm font-semibold rounded-md p-2">
            {{ link.text }}
          </a>
        </div>
      </div>

    </footer>
  </div>
</div>
</template>

<script>
import Toast from './components/Toast.vue';
export default {
  
  components: {
    Toast,
  },
  data() {
    return {
      
      name: 'Portfolio',
      isMenuOpen: false, // State to control menu visibility
      toastMessage: 'تم نسخ الايميل الى الحافضة',
      toastMessage2: 'سيتم اضافة الاعمال لاحقا',
      isToastVisible: false,  // 
      isToastVisible2: false, // Initially hidden
      links: [
        { text: 'لينكدان', url:'https://www.linkedin.com/in/jirou-khalid/' },
        { text: 'فيسبوك' , url:'https://www.facebook.com/profile.php?id=61550237961572' },
        { text: 'تلغرام' , url:'https://t.me/khaled_djeriou' }
      ]
    };
  },
  methods: {
    latestWork(){
      this.isToastVisible2 = true;
      

      // Automatically hide after 3 seconds
      setTimeout(() => {
        this.isToastVisible2 = false;
      }, 2000);
    },
    copyTextInMenu(){
      this.toggleMenu();
      this.copyText();
     
    },
    

   
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen; // Toggle the menu open state
    },
    closeMenu() {
      this.isMenuOpen = false;
    },
    handleOverlayClick() {
      // لا تفعل شيئاً هنا لإبقاء القائمة مفتوحة عند النقر على overlay
    },
   
    copyText() {
      const textToCopy = "khaledjr2018@gmail.com";
      navigator.clipboard.writeText(textToCopy)
        .then(() => {
          // Show toast notification
          // this.$refs.toast.showToast();
          // Toggle the visibility

                this.isToastVisible = true;

          // Automatically hide after 3 seconds
          setTimeout(() => {
            this.isToastVisible = false;
          }, 2000);
        })
        .catch(err => {
          console.error("Failed to copy text: ", err);
        });
    },
  },
};
</script>
<style scoped>
/* Add any additional styles not covered by Tailwind here */
/* Add this in your main CSS or component style section if needed */
</style>