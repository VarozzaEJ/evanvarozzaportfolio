<template>
    <div
        class="group relative rounded-lg p-6 transition-all duration-300 hover:bg-white/5 hover:shadow-lg cursor-pointer">
        <div class="flex flex-col md:flex-row gap-6">
            <!-- Date Range -->
            <div class="text-sm font-medium text-slate-500 uppercase tracking-wider md:w-48 flex-shrink-0">
                {{ date }}
            </div>

            <!-- Content -->
            <div class="flex-1">
                <!-- Title -->
                <h3
                    class="text-lg font-medium text-slate-200 mb-3 group-hover:text-purple-400 transition-colors duration-300 flex items-center gap-2">
                    {{ title }}
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor"
                        class="size-4 mt-1 ms-5 transition ease-in-out delay-0  hover:-translate-y-1 hover:scale-110">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="m4.5 19.5 15-15m0 0H8.25m11.25 0v11.25" />
                    </svg>
                </h3>

                <!-- Description -->
                <p class="text-slate-400 leading-relaxed mb-4">
                    {{ description }}
                </p>

                <!-- Technology Tags -->
                <div class="flex flex-wrap gap-2">
                    <span v-for="tech in technologies" :key="tech"
                        class="px-3 py-1 font-medium bg-green-100 text-green-800 text-xs dark:bg-green-900 dark:text-green-300 rounded-full">
                        {{ tech }}
                    </span>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

defineProps({
    title: {
        type: String,
        required: true,
    },
    description: {
        type: String,
        required: true,
    },
    date: {
        type: String,
        required: true,
    },
})

const technologies = ref(['HTML', 'CSS', 'JavaScript', 'React'])
</script>

<style scoped>
/* Additional custom styles if needed */
</style>