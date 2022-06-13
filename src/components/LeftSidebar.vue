<template>
  <div class="md:mr-5 md:w-1/3 px-4 xl:px-0">
    <div class="ls-slider bg-white p-2 rounded-xl mb-5">
      <carousel :slides="slides" :interval="5000" controls indicators></carousel>
    </div>
    <div class="ls-tag  bg-white rounded-md ">
      <div class="flex bg-gray-200 rounded-t-md justify-between pl-32">
        <p class="font-semibold text-[28px]  py-2 items-center"
          >Теги</p
        >
        <div class="flex justify-between items-center space-x-4 pr-4"> 
          <span class="cursor-pointer" @click="isInput = !isInput"><svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" viewBox="0 0 20 20" fill="#696974">
            <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm1-11a1 1 0 10-2 0v2H7a1 1 0 100 2h2v2a1 1 0 102 0v-2h2a1 1 0 100-2h-2V7z" clip-rule="evenodd" />
          </svg></span>
          <span class="cursor-pointer" @click="editTag"><svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" viewBox="0 0 20 20" fill="#696974">
            <path d="M17.414 2.586a2 2 0 00-2.828 0L7 10.172V13h2.828l7.586-7.586a2 2 0 000-2.828z" />
            <path fill-rule="evenodd" d="M2 6a2 2 0 012-2h4a1 1 0 010 2H4v10h10v-4a1 1 0 112 0v4a2 2 0 01-2 2H4a2 2 0 01-2-2V6z" clip-rule="evenodd" />
          </svg></span>
        </div>
      </div>
      <div class="flex flex-wrap   gap-6 p-6 rounded-b-md">
        <form @submit.prevent="addTag" class="w-full">
         <input type="text" :class="`w-full ${isInput ? 'hidden' : 'block'} border-solid border-2 rounded-md h-10 px-4`" v-model="input" placeholder="Добавить Тег">
        </form>
        <div v-for="(to, index) in categories" :key="index" v-show="isBlocks">
          <a
            href="#"
            class="bg-gray-200 px-4 py-2 rounded-lg  hover:bg-gray-300"
          >
            {{ to }}
          </a>
        </div>
        <div v-for="(to, index) in categories" :key="index" v-show="isHide">
          <input type="text"  :value="to" class="bg-gray-200 px-4 py-2 rounded-lg  hover:bg-gray-300 w-16" @change="toChange"/>
        </div>
      </div>
    </div>
    <div class="ls-info">
      <ul class="px-4 py-6 font-bold leading-8">
        <li>
          Вместе с нами:<span class="font-normal pl-3">3 года 35 дней</span>
        </li>
        <li>
          Отдел:<span class="text-blue-500 font-normal pl-3"
            >Hero Wars Mobile product team</span
          >
        </li>
        <li>Должность/роль:<span class="font-normal pl-3">Team Lead</span></li>
        <li>
          Руководитель:<span class="text-blue-500 font-normal pl-3"
            >Петров И.А.</span
          >
        </li>
        <li>
          Проекты:<span class="text-blue-500 font-normal pl-3"
            >Hero Wars Mobile Unity</span
          >
        </li>
      </ul>
    </div>
    <div class="ls-arch mb-6">
      <div class="ls-tag  bg-white rounded-md">
        <div class="text-center bg-gray-200 rounded-t-md">
          <p class="font-semibold text-[28px]  py-2 items-center"
            >Достижения</p
          >
        </div>
        <div class="pl-5 pt-3 text-[14px] font-semibold text-gray-400">
          <span class="flex">Intranet</span>
        </div>
        <div class="flex flex-wrap   gap-5 px-5 pt-2 pb-5 rounded-b-md">
          <div class="flex" v-for="(to, index) in mess" :key="index">
            <a href="#"><img :src="to" alt="icon" /></a>
          </div>
        </div>
        <div class="pl-5 pt-3 text-[14px] font-semibold text-gray-400">
          <span class="flex">Onboarding</span>
        </div>
        <div class="flex flex-wrap   gap-5 px-5 pt-2 pb-5 rounded-b-md">
          <div class="flex" v-for="(to, index) in mess2" :key="index">
            <a href="#"><img :src="to" alt="icon" /></a>
          </div>
        </div>
        <div class="pl-5 pt-3 text-[14px] font-semibold text-gray-400">
          <span class="flex">Personal</span>
        </div>
        <div class="flex flex-wrap   gap-5 px-5 pt-2 pb-5 rounded-b-md">
          <div class="flex" v-for="(to, index) in mess3" :key="index">
            <a href="#"><img :src="to" alt="icon" /></a>
          </div>
        </div>
      </div>
    </div>
    <div class="ls-about">
      <div class="flex bg-gray-200 rounded-t-md justify-between pl-32">
        <p class="font-semibold text-[28px]  py-2 items-center"
          >О себе</p
        >
        <a href="#" class="pt-4 pr-5"
          ><img src="public/edit.svg" alt="edit"
        /></a>
      </div>
      <ul class="px-4 py-6 font-bold leading-8 bg-white rounded-md">
        <li v-for="(to,i) in infosd" :key="i">
          {{to.infoStatic}}<span class="font-normal pl-3">{{to.infoDinamic}}</span>
        </li>
        
        <li>
          Мои соцсети:
        </li>
        <ul class="flex gap-x-3 text-gray-500">
          <li>
            <a href="#"><img src="public/vk.svg" alt="Social"/></a>
          </li>
          <li>
            <a href="#"><img src="public/instagram.svg" alt="Social"/></a>
          </li>
          <li>
            <a href="#"><img src="public/fb.svg" alt="Social"/></a>
          </li>
        </ul>
      </ul>
    </div>
  </div>
</template>

<script>
import Carousel from "./carousel/Carousel.vue";
export default {
  name: "App",
  components: { Carousel },
  data () {
    return {
    isHide:false,
    isBlocks:true,
     input: '',
     isInput:true,
      slides: [
      "public/car.jpg",
      "public/cat.jpg",
      "public/macedon.jpg",
      "public/new-york.jpg",
      "public/tigr.jpg",
      "public/tornado.jpg",
    ],
      categories: [
        'PHP',
        'Laravel',
        'Lead',
        'HWM',
        'Backend',
        'D&D',
        'BYKE',
        'JS',
        'Jira',
        'Scrum',
        'Agile',
        'Manager'
      ],
      achievements: [
        'public/i-medal1.svg',
        'public/i-medal2.svg',
        'public/i-medal3.svg',
        'public/i-medal4.svg',
        'public/i-medal5.svg',
        'public/i-medal6.svg'
      ],
      
      infosd:[
        {
          infoStatic: 'Дата рождения:',
          infoDinamic: '15 января 1991г.',
        },
        {
          infoStatic: 'Расположение офиса:',
          infoDinamic: 'Москва',
        },
        {
          infoStatic: 'Образование:',
          infoDinamic: 'Окончила ВШЭ по специальности Инженер - исследователь в области наноэлектроники',
        },
        {
          infoStatic: 'Курсы и тренинги:',
          infoDinamic: 'Agile Team Leader от Atlassian University в 2017 году',
        },
        {
          infoStatic: 'Сертификаты:',
          infoDinamic: 'Не имею',
        },
        {
          infoStatic: 'Знание языков:',
          infoDinamic: 'Английский, Русский, Испанский',
        },
        {
          infoStatic: 'Мое хобби:',
          infoDinamic: 'Увлекаюсь серфингом (особо в Москве не посерфишь, но нужно знать места)',
        },
        {
          infoStatic: 'Мои любимые книги:',
          infoDinamic: 'А. Рэнд - “Атлант расправил плечи” М. Дорофеев - “Джедейские техники”',
        },
        {
          infoStatic: 'Мои любимые фильмы:',
          infoDinamic: 'Матрица, Властелин колец, Звездные войны',
        },
      ]
    }
  },
  methods:{
    addTag(){
      this.categories.push(this.input);
      this.input = '';
    },
    editTag(){
      this.isBlocks = !this.isBlocks;
      this.isHide = !this.isHide;
    },
    toChange(){
      this.isBlocks = !this.isBlocks;
      this.isHide = !this.isHide;
    },
  },
  computed: {
    mess(){
     return Array(6).fill().map(() => this.achievements[Math.floor(Math.random()*this.achievements.length)]);
    },
    mess2(){
     return Array(6).fill().map(() => this.achievements[Math.floor(Math.random()*this.achievements.length)]);
    },
    mess3(){
     return Array(6).fill().map(() => this.achievements[Math.floor(Math.random()*this.achievements.length)]);
    }
  }
}
</script>

<style></style>
