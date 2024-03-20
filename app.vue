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
        <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Предложен ли съм за министър?</h2>
        <p class="mt-2 text-lg leading-8 text-gray-600 max-w-lg mx-auto">Звъняли ли са ви непознати номера? <br> Чували
          сте се с Мария Габриел?<br>
          Не е и нужно, все пак може да сте предложени за министър
        </p>
      </div>
      <div action="#" method="POST" class="mx-auto mt-16 max-w-xl sm:mt-20 mb-5">
        <div class="grid grid-cols-1 gap-x-8 gap-y-6 sm:grid-cols-2">
          <div class="sm:col-span-2">
            <label for="ЕГН" class="block text-sm font-semibold leading-6 text-gray-900">ЕГН</label>
            <div class="mt-2.5">
              <input type="text" v-model="egn" name="ЕГН" id="ЕГН" autocomplete="organization"
                class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
            </div>
          </div>
          <p v-if="showError" class="text-red-500 col-span-2">
            Моля въведете валидно ЕГН от точно 10 цифри.
          </p>
        </div>
        <div class="mt-10">
          <button @click="submit"
            class="block w-full rounded-md bg-indigo-600 px-3.5 py-2.5 text-center text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Провери</button>
        </div>
      </div>
      <Transition  name="slide-fade">

        <div v-if="showSuccess" class="aspect-w-16 aspect-h-9 max-w-xl mx-auto ">
          <p class="text-black text-2xl mb-3">
            Не са открити номинации за министър в базата данни
          </p>
          <!-- <img src="/mara.jpg" class="object-cover w-full h-full rounded-xl"> -->
        </div>
      </Transition>
    </div>

  </div>
</template>
<script setup>
import { ref } from 'vue'
import { ChevronDownIcon } from '@heroicons/vue/20/solid'
import { Switch, SwitchGroup, SwitchLabel } from '@headlessui/vue'

const errorMessage = ''

const showError = ref(false)
const showSuccess = ref(false)
const egn = ref('')

function submit() {
  showSuccess.value = false
  if (egn.value.length !== 10) {
    showError.value = true
    return
  }
  showError.value = false
  showSuccess.value = true
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