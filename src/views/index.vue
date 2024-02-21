<template>
    <main class="w-full  flex flex-col justify-center items-center bg-gray-100">
        <div class="w-[90%] h-28 flex justify-between mt-10">
            <div class="" >
                <input v-model="userSelect" type="text" class="relative w-[500px] h-14  pl-20 text-lg rounded-[15px]" placeholder="Search for country">
                <svg @click="selectFeiltr" class="w-10 h-7 absolute top-14 left-32" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"><path d="M18.031 16.6168L22.3137 20.8995L20.8995 22.3137L16.6168 18.031C15.0769 19.263 13.124 20 11 20C6.032 20 2 15.968 2 11C2 6.032 6.032 2 11 2C15.968 2 20 6.032 20 11C20 13.124 19.263 15.0769 18.031 16.6168ZM16.0247 15.8748C17.2475 14.6146 18 12.8956 18 11C18 7.1325 14.8675 4 11 4C7.1325 4 4 7.1325 4 11C4 14.8675 7.1325 18 11 18C12.8956 18 14.6146 17.2475 15.8748 16.0247L16.0247 15.8748Z"></path></svg>
            </div>
            <div>
                <select name="pets" id="pet-select" class="w-40 h-14 border rounded-[15px] p-3">
                <option value="" class="text-center text-xl">filter by region</option>
                <option class="text-center text-xl" v-for="(iteamSlect , indSe) in countriesApi" key="indse" value="">{{iteamSlect && iteamSlect.region ? iteamSlect.region:'-'}}
                </option>
                
</select>
            </div>
        </div>
     <section class="w-[90%] h-auto flex flex-col items-center  lg:grid lg:grid-cols-4  gap-y-10  mt-16">
        <div v-for="(iteam , indx) in countriesApi" key="indx" class="w-72 h-auto  flex flex-col gap-y-10 p-5">
            <div class="h-1/2">
                <img class="h-full" :src=iteam.flags.png alt="">
            </div>
            <div>
                <p class="text-lg font-bold ">{{iteam && iteam.name ? iteam.name:'-'}}</p>
            </div>
            <div>
                <h2 class="text-xl">Population : {{iteam && iteam.population ? iteam.population:'-'}}</h2>
                <h2 class="text-xl">Region : {{iteam && iteam.region ? iteam.region:'-'}}</h2>
                <h2 class="text-xl">Capital : {{iteam && iteam.capital ? iteam.capital:'-'}}</h2>
                <h2 class="text-xl">languages : {{iteam && iteam.languages.nativeName ? iteam.languages.nativeName:'-'}}</h2>
                <h2 class="text-xl">demonym : {{iteam && iteam.demonym ? iteam.demonym:'-'}}</h2>
            </div>
        </div>
     </section>
    </main>
  </template>
  
  <script>
//   import axios from "axios";
import jsonCountry from "../countries.json";
  export default {
    data() {
      return {
       countriesApi:jsonCountry,
       userSelect:'',
       selectedFilter:[],
      };
    },
    mounted() {
     
    },
  
    computed: {
            
    },
    methods: {
     selectFeiltr(){
        // if(this.countriesApi.name){
        //     console.log("ok");
        // }else{
        //     console.log('nabod');
        // }
        // console.log(this.countriesApi);
      if(this.countriesApi.filter((e)=>{
        e.name.includes(this.userSelect)
      })){
       alert('ok');
        
      }else{
        alert('msg');
      }
     }
  
    },
  };
  </script>
  
  <style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body , main , *{
    font-family: "Nunito Sans", sans-serif;
  font-optical-sizing: auto;
  font-weight: weight;
  font-style: normal;
  font-variation-settings:
    "wdth" 100,
    "YTLC" 500;
  }
  </style>