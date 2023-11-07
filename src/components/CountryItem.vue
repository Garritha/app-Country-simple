<script setup lang="ts">
import { defineProps } from 'vue';
import { Country } from '../models/country.models.ts';

interface Props {
    country: Country;

}
defineProps<Props>();
</script>



<template>
    <div class="h-56 sm:h-36 ">
        <img  class="h-56 sm:h-36  w-full "  
         :src="country.flags.png" 
         :alt="country.flags.alt">
    </div>
    <h4 class="text-xl font-bold  text-gray-500">{{ country.name.common }}</h4>
    <p class="text-sm text-gray-400">
       Capital: 
        <span  v-for="capital in country.capital" class="font-bold">{{ capital }}
        
        </span>
    </p>
    <p class="text-sm text-gray-400">
    Languages:
    <span v-for="(language, index) in country.languages" :key="index" class="font-bold">
      {{ language }}
      <span v-if="index < country.languages.length - 1">,</span>
    </span>
  </p>
    <p class="text-sm text-gray-400"  >
        Population:
         <span class="font-bold"> {{ country.population?.toLocaleString() }}  </span> 
    </p>
    <p class="text-sm text-gray-400">
        Region: 
        <span class=" font-bold">{{  country.region }}</span>
    </p>   
</template>