<template>
  <div class=" mr-5 w-full sm:w-1/3">
    <div class="ls-slider bg-white p-2 rounded-xl mb-5">
      <div class="text-center">
        <span
          class="font-semibold lg:text-lg text-sm bg-gray-200  py-2 items-center px-20 flex rounded-t-md"
          >Полякова Майя</span
        >
        <img src="public/slider.jpg" alt="Slider" class="w-full"/>
      </div>
    </div>
    <div class="ls-tag  bg-white rounded-md ">
      <div class="flex bg-gray-200 rounded-t-md lg:flex-nowrap flex-wrap text-sm xl:px-28 lg:px-20 md:px-15 sm:px-10 text-center">
        <span class="font-semibold lg:text-lg text-sm  py-2 items-center text-center "
          >Теги</span
        >
        <a href="#" class="pt-5">Смотреть все</a>
      </div>
      <div class="flex flex-wrap   gap-5 p-5 rounded-b-md">
        <div v-for="(to, index) in categories" :key="index">
          <a
            href="#"
            class="bg-gray-200 px-4 py-2 rounded-lg  hover:bg-gray-300"
          >
            {{ to }}
          </a>
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
        <div class="flex bg-gray-200 rounded-t-md">
          <span class="font-semibold text-[28px]  py-2 items-center px-28"
            >Достижения</span
          >
        </div>
        <div class="pl-5 pt-3 text-[14px] font-semibold text-gray-400">
          <span class="flex">Intranet</span>
        </div>
        <div class="flex flex-wrap   gap-5 p-5 rounded-b-md">
          <div class="flex" v-for="(to, index) in achievements" :key="index">
            <a href="#"><img :src="to" alt="icon" /></a>
          </div>
        </div>
        <div class="pl-5 pt-3 text-[14px] font-semibold text-gray-400">
          <span class="flex">Onboarding</span>
        </div>
        <div class="flex flex-wrap   gap-5 p-5 rounded-b-md">
          <div class="flex" v-for="(to, index) in achievements" :key="index">
            <a href="#"><img :src="to" alt="icon" /></a>
          </div>
        </div>
        <div class="pl-5 pt-3 text-[14px] font-semibold text-gray-400">
          <span class="flex">Personal</span>
        </div>
        <div class="flex flex-wrap   gap-5 p-5 rounded-b-md">
          <div class="flex" v-for="(to, index) in achievements" :key="index">
            <a href="#"><img :src="to" alt="icon" /></a>
          </div>
        </div>
      </div>
    </div>
    <div class="ls-about">
      <div class="flex bg-gray-200 rounded-t-md">
        <span class="font-semibold text-[28px]  py-2 items-center px-36"
          >Теги</span
        >
        <a href="#" class="pt-4"
          ><img src="public/edit.svg" alt="edit"
        /></a>
      </div>
      <ul class="px-4 py-6 font-bold leading-8 bg-white rounded-md">
        <li>
          Дата рождения:<span class="font-normal pl-3">15 января 1991г.</span>
        </li>
        <li>
          Расположение офиса:<span class="font-normal pl-3"
            >Окончила ВШЭ по специальности Инженер - исследователь в области
            наноэлектроники</span
          >
        </li>
        <li>
          Курсы и тренинги:<span class="font-normal pl-3"
            >Agile Team Leader от Atlassian University в 2017 году</span
          >
        </li>
        <li>Сертификаты:<span class="font-normal pl-3">Не имею</span></li>
        <li>
          Знание языков:<span class="font-normal pl-3"
            >Английский, Русский, Таджикский</span
          >
        </li>
        <li>
          Мое хобби:<span class="font-normal pl-3"
            >Увлекаюсь серфингом (особо в Москве не посерфишь, но нужно знать
            места)</span
          >
        </li>
        <li>
          Мои любимые книги:<span class="font-normal pl-3"
            >А. Рэнд - “Атлант расправил плечи” М. Дорофеев - “Джедейские
            техники”</span
          >
        </li>
        <li>
          Мои любимые фильмы:<span class="font-normal pl-3"
            >Матрица, Властелин колец, Звездные войны, Диктатор</span
          >
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
export default {
  data () {
    return {
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
      ]
    }
  }
}
</script>

<style></style>
