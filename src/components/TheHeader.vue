<template>
<div class="header-content">
   <nav class="bg-white py-2 items-center">
    <div class=" mx-auto h-20  xl:container lg:container md:container sm:container">
      <div class="relative flex items-center justify-between h-16">
        <div class="absolute inset-y-0 left-0 flex items-center md:hidden">
          <button
            type="button"
            @click="isMobile = !isMobile"
            :class="`${isMobile ? 'bg-gray-700 ' : 'bg-white text-gray-500'} inline-flex items-center justify-center p-2 rounded-md text-gray-400 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white`"
            aria-controls="mobile-menu"
            aria-expanded="false"
          >
            <svg
              class="block h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="2"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M4 6h16M4 12h16M4 18h16"
              />
            </svg>

            <svg
              class="hidden h-6 w-6"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="2"
              stroke="currentColor"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
        <div
          class="flex-1 flex items-center justify-center sm:items-stretch sm:justify-start"
        >
          <div class="hidden md:flex flex-shrink-0 flex items-center mr-10 items-center">
            <a href="/" class="text-[28px] text-[#171725] font-bold"
              >GMPortal</a
            >
          </div>
          <div
            class="hidden md:flex items-center p-2.5 lg:w-1/2 max-w-screen-md justify-end p-2.5 pl-8 md:pl-12 md:px-8 lg:px-0 flex-1"
          >
            <div class="flex w-full h-12 relative ">
              <input
                type="text"
                name=""
                id=""
                placeholder="Поиск..."
                class="lg:block hidden border border-grey-300 w-full px-3 shadow-inner rounded-2xl focus:outline-none focus:border-blue-700 bg-gray-50"
              />
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-6 w-6 absolute right-0 my-3 mx-4 text-gray-600"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                stroke-width="2"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
                />
              </svg>
            </div>
          </div>
          <div class="hidden md:block items-center">
            <div class="flex space-x-4">
              <a
                href="#"
                class="text-gray-500 hover:underline px-3 pt-6 rounded-md text-sm font-medium"
                aria-current="page"
                >Главная</a
              >

              <a
                href="#"
                class="text-gray-500 hover:underline px-3 pt-6 rounded-md text-sm font-medium"
                >Сервисы</a
              >

              <a
                href="#"
                class="text-gray-500 hover:underline px-3 pt-6 rounded-md text-sm font-medium"
                >Календарь</a
              >

              <a
                href="#"
                class="text-gray-500 hover:underline px-3 pt-6 rounded-md text-sm font-medium"
                >Настройки</a
              >
              <a
                href="#"
                class="text-gray-500 hover:underline px-3 pt-6 rounded-md text-sm font-medium"
                >Помощь</a
              >
            </div>
          </div>
        </div>
        <div
          class="absolute inset-y-0 right-0 flex items-center pr-2 sm:static sm:inset-auto sm:ml-6 sm:pr-0"
        >
          <div class="ml-5 relative">
            <div>
              <button
                type="button"
                class=" flex text-sm rounded-full focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-blue-600 focus:ring-white bg-gray-300"
                id="user-menu-button"
                aria-expanded="false"
                aria-haspopup="true"
              >
                <span class="sr-only">User</span>
                <img
                  class="h-12 w-12 rounded-full"
                  src="public\prog.jpg"
                  alt=""
                />
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
    <Transition>
      <div v-if="isMobile" class="px-4 md:px-0" id="mobile-menu">
        <div class="px-2 pt-2 pb-3 space-y-1">
          <div
            class="sm:flex items-center lg:w-1/2 max-w-screen-md justify-end md:pl-12 md:px-8 lg:px-0 flex-1"
          >
            <div class="flex w-full h-12 relative ">
              <input
                type="text"
                name=""
                id=""
                placeholder="Поиск..."
                class=" border border-grey-300 w-full px-3 shadow-inner rounded-2xl focus:outline-none focus:border-blue-700 bg-gray-50"
              />
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-6 w-6 absolute right-0 my-3 mx-4 text-gray-600"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                stroke-width="2"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
                />
              </svg>
            </div>
            <div></div>
          </div>
          <a
            href="#"
            class="bg-gray-200 hover:bg-gray-300 block px-3 py-2 rounded-md text-base font-medium"
            aria-current="page"
            >Главная</a
          >

          <a
            href="#"
            class=" bg-gray-200 hover:bg-gray-300  block px-3 py-2 rounded-md text-base font-medium"
            >Сервисы</a
          >

          <a
            href="#"
            class=" bg-gray-200 hover:bg-gray-300  block px-3 py-2 rounded-md text-base font-medium"
            >Календарь</a
          >

          <a
            href="#"
            class=" bg-gray-200 hover:bg-gray-300  block px-3 py-2 rounded-md text-base font-medium"
            >Настройки</a
          >
          <a
            href="#"
            class=" bg-gray-200 hover:bg-gray-300  block px-3 py-2 rounded-md text-base font-medium"
            >Помощь</a
          >
        </div>
      </div>
    </Transition>
  </nav>
  <div class="header-img container mx-auto py-6  xl:container lg:container md:container sm:container px-4 sm:px-0">
    <img src="public\header-img.png" alt="IMG" class="w-full" />
  </div>
</div>
 
</template>

<script>
export default {
  data () {
    return {
    isMobile: false
    }
  },
}
</script>

<style>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
