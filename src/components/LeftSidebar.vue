<template>
<div class="w-3/1 max-w-[400px]">
    <div class="ls-slider bg-white p-2 rounded-xl mb-5">
       <div class="text-center">
           <span class="font-semibold text-[28px] bg-gray-200 py-2 items-center px-20 flex rounded-t-md">Полякова Майя</span>
           <img src="public/slider.jpg" alt="Slider">
       </div>
    </div>
    <div class="ls-tag  bg-white rounded-md">
            <div class="flex bg-gray-200 rounded-t-md">
                <span class="font-semibold text-[28px]  py-2 items-center px-2">Теги</span>
                <a href="#" class="">Смотреть все</a>
           </div>
           <div class="flex flex-wrap   gap-5 p-5 rounded-b-md">
            <div  v-for="(to,index) in categories" :key="index">
                <a href="#" class="bg-gray-200 px-4 py-2 rounded-lg  hover:bg-gray-300">
                    {{ to }}
                </a>
            </div>
           </div>
    </div>
    <div class="ls-arch">
        <ul class="px-4 py-6 font-bold">
            <li>Вместе с нами:<span class="font-normal pl-3">3 года 35 дней</span></li>
            <li>Отдел:<span class="text-blue-500 font-normal pl-3">Hero Wars Mobile product team</span></li>
            <li>Должность/роль:<span class="font-normal pl-3">Team Lead</span></li>
            <li>Руководитель:<span class="text-blue-500 font-normal pl-3">Петров И.А.</span></li>
            <li>Проекты:<span class="text-blue-500 font-normal pl-3">Hero Wars Mobile Unity</span></li>
        </ul>
    </div>
    <div class="ls-info">
        
    </div>
    <div class="ls-about">
        
    </div>
</div>
</template>

<script>
    export default {

    data() {
        return {
            categories: [
            "PHP",
            "Laravel",
            "Lead" ,
            "HWM" ,
            "Backend" ,
            "D&D" ,
            "BYKE" ,
            "JS",
            "Jira",
            "Scrum" ,
            "Agile" ,
            "Manager"
            ]
        };
    },

}
</script>

<style>

</style>