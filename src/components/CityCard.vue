<template>
    <div
      class="flex flex-row justify-between items-center py-6 px-3 bg-weather-secondary rounded-md shadow-md cursor-pointer"
    >
      <div class="flex flex-col">
        <h2 class="text-3xl">{{ city.city }}</h2>
        <h3>{{ city.state }}</h3>
      </div>

      <div>
        <img
          class="md:w-[100px] w-[70px] h-auto"
          :src="
            `https://openweathermap.org/img/wn/${city.weather.weather[0].icon}@2x.png`
          "
          alt=""
        />
      </div>
  
      <div class="flex flex-col gap-2">
        <p class="text-3xl self-end">
          {{ Math.round(city.weather.main.temp) }}&deg;
        </p>
        <div class="flex gap-2">
          <span class="text-xs">
            H:
            {{ Math.round(city.weather.main.temp_max) }}&deg;
          </span>
          <span class="text-xs">
            L:
            {{ Math.round(city.weather.main.temp_min) }}&deg;
          </span>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  defineProps({
    city: {
      type: Object,
      default: () => {},
    },
  });
  </script>