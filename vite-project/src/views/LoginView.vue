<script setup lang="ts">
import {  reactive, ref } from 'vue'
import { RouterLink } from 'vue-router';
import customModal from '../components/customModal.vue';
const rememberValue = ref(true)

// Reactive State
const isModalVisible = ref(false);

// Methods
const openModal = () => {
  isModalVisible.value = true;
};

const closeModal = () => {
    information.username = '';
    information.password = '';
  isModalVisible.value = false;
};


const information = reactive({
    username : '',
    password : ''
})
const switchRememberVal = () => {
    rememberValue.value = !rememberValue.value;
}
</script>
<template>
        <div class="container-fluid mx-auto ">
        <div class="flex">
            <div class="basis-3/5 bg-slate-200 p-4 min-h-screen">Img mock {{ information.username + information.password }}</div>

            <div class="basis-2/5 bg-white min-h-screen">

                <div class="flex flex-col items-center justify-center min-h-screen">

                    <div class="flex flex-col items-center text-center">
                        <img src="../assets/logo.png" class="w-36 my-4" alt="Logo" />
                        <h1 class="font-bold text-3xl">Welcome to Choco CDP</h1>
                        <div class="my-3">
                            <h2 class="font-normal text-slate-500 text-md">
                                Please Login. You need to login to access this page
                            </h2>
                            <h2 class="font-normal text-slate-500 text-md">
                                Please enter your username and password and click login
                            </h2>
                        </div>
                    </div>

                    <div class="flex flex-col items-center mt-4 p-4">
                        <input type="text" placeholder="Username" v-model="information.username" class="border-b-2 border-gray-300 w-96 p-2 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 my-2">
                        <input type="password" placeholder="Password" v-model="information.password" class="border-b-2 border-gray-300 w-96 p-2 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 my-2" />
                        <div class="flex flex-row justify-between w-full mt-2">
                            <div class="flex salign-center">
                                <input type="checkbox" class="checkbox checkbox-primary mr-2" :checked="rememberValue" @click="switchRememberVal"/>
                                <span class="text-blue-500" @click="switchRememberVal">Remember me</span>
                            </div>
                            <RouterLink to="/forgetPassword">
                                <a class="text-blue-500">Forgot Password?</a>
                            </RouterLink>
                        </div>
                        <button class="btn w-full my-4 bg-blue-500 text-white"  @click="openModal">
                            login
                        </button>
                        <div class="divider text-slate-300">OR</div>
                    </div>


                </div>
            </div>
        </div>
    </div>

    <customModal :isVisible="isModalVisible" @close="closeModal">
      <!-- <button @click="closeModal" class="bg-red-500 text-white px-4 py-2 rounded-md hover:bg-red-600">
        Close Modal
      </button> -->
    </customModal>


</template>