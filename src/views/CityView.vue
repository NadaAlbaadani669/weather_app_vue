<template>
    <div>
        <Suspense>
            <AsyncCityView />
            <template #fallback>
               <CityViewSekelton />
            </template>
        </Suspense>
    </div>
</template>

<script setup>
import AsyncCityView from '../components/AsyncCityView.vue';
import CityViewSekelton from '../components/CityViewSekelton.vue';
</script>
