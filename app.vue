<template>
  <div>
    <div class="isolate bg-white px-6 py-24 sm:py-32 lg:px-8">
      <div class="absolute inset-x-0 top-[-10rem] -z-10 transform-gpu overflow-hidden blur-3xl sm:top-[-20rem]"
        aria-hidden="true">
        <div
          class="relative left-1/2 -z-10 aspect-[1155/678] w-[36.125rem] max-w-none -translate-x-1/2 rotate-[30deg] bg-gradient-to-tr from-[#ff80b5] to-[#9089fc] opacity-30 sm:left-[calc(50%-40rem)] sm:w-[72.1875rem]"
          style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)" />
      </div>
      <div class="mx-auto max-w-2xl text-center">
        <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Предложени ли сте за министър?</h2>
        <p class="mt-2 text-lg leading-8 text-gray-600 max-w-lg mx-auto">Звъняли са ви непознати номера? <br> Чували
          сте се с Мария Габриел?<br>
          Не е и нужно, все пак може да сте предложени за министър.
        </p>
      </div>
      <div action="#" method="POST" class="mx-auto mt-16 max-w-xl sm:mt-20 mb-5">
        <div class="grid grid-cols-1 gap-x-8 gap-y-6 sm:grid-cols-2">
          <div class="sm:col-span-2">
            <label for="триИмена" class="block text-sm font-semibold leading-6 text-gray-900">Пълно име</label>
            <div class="mt-2.5">
              <input type="text" v-model="fullName" placeholder="Андрей Цеков" name="триИмена" id="триИмена"
                autocomplete="name"
                class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
            </div>
          </div>
          <Transition name="slide-fade">

            <p v-if="showError" class="text-red-500 col-span-2">
              Моля въведете поне две име на кирилица.
            </p>
          </Transition>
        </div>
        <div class="mt-10">
          <button @click="submit"
            class="block w-full rounded-md bg-indigo-600 px-3.5 py-2.5 text-center text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Провери</button>
        </div>

        <div class="fixed left-0 right-0 bottom-10 flex justify-center items-center">

          <a href="https://twitter.com/Georgi_________"
            class="text-gray-400 flex justify-center items-center gap-x-2 mt-3 ">
            Georgi
            <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="100" height="100" class="size-6 fill-gray-400"  viewBox="0 0 24 24">
<path d="M 2.3671875 3 L 9.4628906 13.140625 L 2.7402344 21 L 5.3808594 21 L 10.644531 14.830078 L 14.960938 21 L 21.871094 21 L 14.449219 10.375 L 20.740234 3 L 18.140625 3 L 13.271484 8.6875 L 9.2988281 3 L 2.3671875 3 z M 6.2070312 5 L 8.2558594 5 L 18.033203 19 L 16.001953 19 L 6.2070312 5 z"></path>
</svg>
          </a>
          <a href="https://github.com/gkkirilov/bgminister"
            class="text-gray-400 flex justify-center items-center gap-x-2 mt-3 ml-2 ">
            <svg x="0px" y="0px" width="100" height="100" class="size-6 fill-gray-400" viewBox="0 0 30 30">
              <path
                d="M15,3C8.373,3,3,8.373,3,15c0,5.623,3.872,10.328,9.092,11.63C12.036,26.468,12,26.28,12,26.047v-2.051 c-0.487,0-1.303,0-1.508,0c-0.821,0-1.551-0.353-1.905-1.009c-0.393-0.729-0.461-1.844-1.435-2.526 c-0.289-0.227-0.069-0.486,0.264-0.451c0.615,0.174,1.125,0.596,1.605,1.222c0.478,0.627,0.703,0.769,1.596,0.769 c0.433,0,1.081-0.025,1.691-0.121c0.328-0.833,0.895-1.6,1.588-1.962c-3.996-0.411-5.903-2.399-5.903-5.098 c0-1.162,0.495-2.286,1.336-3.233C9.053,10.647,8.706,8.73,9.435,8c1.798,0,2.885,1.166,3.146,1.481C13.477,9.174,14.461,9,15.495,9 c1.036,0,2.024,0.174,2.922,0.483C18.675,9.17,19.763,8,21.565,8c0.732,0.731,0.381,2.656,0.102,3.594 c0.836,0.945,1.328,2.066,1.328,3.226c0,2.697-1.904,4.684-5.894,5.097C18.199,20.49,19,22.1,19,23.313v2.734 c0,0.104-0.023,0.179-0.035,0.268C23.641,24.676,27,20.236,27,15C27,8.373,21.627,3,15,3z">
              </path>
            </svg>
          </a>
          
        </div>
      </div>
      <Transition name="slide-fade">

        <div v-if="showSuccess" class="aspect-w-16 aspect-h-9 max-w-xl mx-auto ">
          <p class="text-black text-2xl mb-3">
            Не са открити номинации за министър в базата данни.
          </p>
          <!-- <img src="/mara.jpg" class="object-cover w-full h-full rounded-xl"> -->
        </div>
      </Transition>
      <Transition name="slide-fade">
        <div v-if="showSuccessminister" class="aspect-w-16 aspect-h-9 max-w-xl mx-auto ">
          <p class="text-black text-2xl mb-3 text-red-600 text-center">
            ⚠️ Министър си, крий се бързо. ⚠️
          </p>
          <img src="/mara.jpg" class="object-cover w-full h-full rounded-xl">
        </div>
      </Transition>
    </div>

  </div>
</template>
<script setup>

import { ref } from 'vue'

const showError = ref(false)
const showSuccess = ref(false)
const showSuccessminister = ref(false)
const fullName = ref('')

const ministers = [
  'Мария Габриел',
  'Николай Денков',
  'Асен Василев',
  'Калин Стоянов',
  'Андрей Цеков',
  'Иванка Шалапатова',
  'Христо Гаджев',
  'Атанас Славов',
  'Галин Цоков',
  'Катя Панева',
  'Кръстьо Кръстев',
  'Ивелина Василева',
  'Кирил Вътев',
  'Георги Гвоздейков',
  'Росен Желязков',
  'Богдан Богданов',
  'Жечо Станков',
  'Валентин Мундров',
  'Зарица Динкова',
  'Димитър Илиев',
]
function containsCyrillic(text) {
  // Regular expression to match Cyrillic characters
  const cyrillicPattern = /\p{Script=Cyrillic}/u;
  // Test if the text contains any Cyrillic characters
  return cyrillicPattern.test(text);
}
function submit() {
  showSuccess.value = false

  if (fullName.value.length <= 10 || !containsCyrillic(fullName.value)) {
    showError.value = true
    return
  }

  for (const name of ministers) {
    if (name.indexOf(fullName.value) !== -1) {
      showSuccessminister.value = true

      setTimeout(() => {
        showSuccessminister.value = false
      }, 10000);
      return
    }
  }

  showError.value = false
  showSuccess.value = true

  setTimeout(() => {
    showSuccess.value = false
  }, 10000);
}

</script>
<style>
.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateY(40px);
  opacity: 0;
}
</style>