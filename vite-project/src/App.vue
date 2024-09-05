<script setup lang="ts">
import { useCounterStore } from "./stores/Counter.js"
import {  ref } from 'vue'

const rememberValue = ref(true)

const switchRememberVal = () => {
    rememberValue.value = !rememberValue.value;
}

const counter = useCounterStore()
</script>

<template>
    <!-- <HelloWorld msg="prop pass" /> -->
    <div class="container-fluid mx-auto px-4">
        <div class="flex">
            <div class="basis-3/5 bg-slate-200 p-4 min-h-screen">Img mock {{ counter.name }}</div>

            <div class="basis-2/5 bg-white min-h-screen">

                <div class="flex flex-col items-center justify-center min-h-screen">

                    <div class="flex flex-col items-center text-center">
                        <img src="./assets/logo.png" class="w-36 my-4" alt="Logo" />
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
                        <input type="text" placeholder="Username" class="input input-bordered w-96 my-2" />
                        <input type="password" placeholder="Password" class="input input-bordered w-96 my-2" />
                        <div class="flex flex-row justify-between w-full mt-2">
                            <div class="flex salign-center">
                                <input type="checkbox" class="checkbox checkbox-primary mr-2" :checked="rememberValue" @click="switchRememberVal"/>
                                <span class="text-blue-500" @click="switchRememberVal">Remember me</span>
                            </div>
                            <a class="text-blue-500">Forgot Password?</a>
                        </div>
                        <button class="btn w-full my-4 bg-blue-500 text-white">
                            login
                        </button>
                        <div class="divider text-slate-300">OR</div>
                    </div>


                </div>
            </div>
        </div>
    </div>
</template>

<style scoped></style>
