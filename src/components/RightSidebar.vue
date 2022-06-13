<template>
    <div class="mx-auto xl:px-0 w-full md:mt-0 mt-5">
        <div class="new-post rounded-xl w-full bg-white px-8 py-5 mb-5">
            <div class="flex justify-between items-center border-b pb-5">
                <div class="new-post_span">
                    <span class="lg:text-[24px] text-[18px] font-bold text-[#696974]">Новый пост</span>
                </div>
                <div class="new-post_format flex gap-x-5 items-center">
                    <span class="cursor-pointer text-gray-400 hover:bg-gray-800 hover:rounded-sm" @click="textNormal">Normal</span>
                    <ul class="flex gap-x-2">
                        <li class="cursor-pointer text-gray-400 hover:bg-gray-800 hover:rounded-sm" @click="textBold" ><img src="public/edit-icon.svg" alt="icon"></li>
                        <li class="cursor-pointer text-gray-400 hover:bg-gray-800 hover:rounded-sm" @click="textItalic"><img src="public/edit-icon1.svg" alt="icon"></li>
                        <li class="cursor-pointer text-gray-400 hover:bg-gray-800 hover:rounded-sm" @click="textUnderline"><img src="public/edit-icon3.svg" alt="icon"></li>
                    </ul>
                    <ul class="flex gap-x-2">
                        <li class="cursor-pointer text-gray-400 hover:bg-gray-800 hover:rounded-sm" @click="textLeft"><img src="public/edit-icon5.svg" alt="icon"></li>
                        <li class="cursor-pointer text-gray-400 hover:bg-gray-800 hover:rounded-sm" @click="texJustify"><img src="public/edit-icon6.svg" alt="icon"></li>
                    </ul>
                    <ul class="flex gap-x-2">
                        <li class="cursor-pointer text-gray-400 hover:bg-gray-800 hover:rounded-sm" @click="textPy"><img src="public/edit-icon7.svg" alt="icon"></li>
                    </ul>
                </div>
            </div>
            <form class="flex justify-between pt-5" @submit.prevent="addPost">
                <div class="new-post_img ">
                    <img src="public/favicon.ico" alt="Icon">
                </div>
                <div class="new-post_input focus:outline-none focus:border-none">
                    <input type="text" v-model="value" name="" id="" placeholder="Что у тебя на уме?" :class="`${isBold ? 'font-extrabold' : 'font-normal'} ${isItalic ? 'italic' : 'not-italic'} ${isUnderline ? 'underline' : 'no-underline'} ${isLeft ? 'text-left' : ''} ${isJustify ? 'text-justify' : 'font-normal'} ${isPy ? 'font-bold' : 'font-normal'} px-5 py-2  focus:outline-none focus:border-none placeholder:font-normal placeholder:not-italic placeholder:no-underline   xl:w-[35rem] lg:w-[30rem] md:w-[25rem] sm:w-[20rem]`">
                </div>
                <div class="new-post_btn">
                    <button class="bg-[#3DD598] hover:bg-[#2fb37c] px-2 lg:px-6 py-3 rounded-lg lg:text-lg text-sm text-white font-bold flex-none" @click="addPost">Опубликовать</button>
                </div>
            </form>
        </div>

        <div class="new-post rounded-xl w-full bg-white px-8 py-5 mb-5" v-for="addPost in post" :key="addPost.id" :id="addPost.id">
            <div class="flex items-center">
                    <div class="pr-4">
                        <img class="" src="public/favicon.ico" alt="icon">
                    </div>
                    <div class="items-center pb-2">
                        <span class="text-[#171725] text-[16px] font-semibold">Amirjon Rajabov</span>
                        <p class="text-[#92929D]">{{addPost.date}}</p>
                    </div>
            </div>
            <div class="flex pt-2 justify-between">
              <div class="flex flex-wrap">
                <p class="text-[#44444F] break-all">{{
                    addPost.text
                  }}</p>
              </div>
             <div class="post-like hover:cursor-pointer flex">
                <svg width="24px" height="24px" @click="clickLike(addPost.id)" viewBox="0 0 36 36" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" class="iconify iconify--twemoji" preserveAspectRatio="xMidYMid meet"><path :fill="`${count % 2 !== 0  ? '#DD2E44' : '#92929D'}`" d="M35.885 11.833c0-5.45-4.418-9.868-9.867-9.868c-3.308 0-6.227 1.633-8.018 4.129c-1.791-2.496-4.71-4.129-8.017-4.129c-5.45 0-9.868 4.417-9.868 9.868c0 .772.098 1.52.266 2.241C1.751 22.587 11.216 31.568 18 34.034c6.783-2.466 16.249-11.447 17.617-19.959c.17-.721.268-1.469.268-2.242z"></path></svg><span class="flex items-center px-1">{{count}}</span>
            </div>
            </div>
        </div>
            
    </div>
</template>

<script>
export default {
  data () {
    return {
    count: 0,
    value:"",
    isBold:false,
    isItalic:false,
    isUnderline:false,
    isLeft:false,
    isJustify:false,
    isPy:false,
      post: [],
    }
  },
  methods:{
      addPost(){
          if(this.value.trim() === '') return;
                  this.post.push({
                  count:0,
                  id: Date.now(),
                  text: this.value.trim(),
                  date:`${new Date().getDate()} ${new Date().toLocaleString('default', { month: 'long' })} ${new Date().getHours()} :  ${new Date().getMinutes()}`
            }
          );
          this.value = "";
        
      },
    
        textBold(){
            this.isBold = !this.isBold;
        },
        textItalic(){
            this.isItalic = !this.isItalic;
        },
        textUnderline(){
            this.isUnderline = !this.isUnderline;
        },
        textLeft(){
            this.isLeft = !this.isLeft;
        },
        texJustify(){
            this.isJustify = !this.isJustify;
        },
        textPy(){
            this.isPy = !this.isPy;
        },
        textNormal(){
             this.isBold = this.isItalic  = this.isUnderline = this.isLeft = this.isJustify = this.isPy = false;
        },
        clickLike(index){   
            if(this.count %2 === 0){
                this.count++;
            }else this.count--;
        }
  }
}
</script>

<style>

</style>