<template>
    <div class="flex justify-between py-6 px-3 bg-weather-secondary rounded-md shadow-md cursor-pointer">
       <div class="flex flex-col felx-1">
            <h2 class="text-3xl">{{ city.city }}</h2>
            <h3>{{ city.state }}</h3>
       </div>

       <div class="flex flex-col gap-2">
            <p class="text-3xl self-end">
                {{ weatherCel(city.weather.main.temp) }}&deg;
            </p>
            <div class="flex gap-2">
                <span class="text-xs">
                    H: {{ weatherCel(city.weather.main.temp_max) }}&deg;
                </span>
                <span class="text-xs">
                    L: {{ weatherCel(city.weather.main.temp_min) }}&deg;
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

const weatherCel = (x)=>{
    const y = Math.round((x-32)*(5/9));
    return y;
}
</script>
