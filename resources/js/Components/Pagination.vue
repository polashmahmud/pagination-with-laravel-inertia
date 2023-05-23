<script setup>
    import { Link } from '@inertiajs/vue3';
    defineProps({
        pagination: Object
    })
</script>

<template>
    <nav class="flex justify-center items-center">
        <template v-for="link in pagination.links" :key="link.label" >
            <Link 
                preserve-scroll
                :href="link.url ?? ''"
                v-html="link.label"
                class="flex justify-center items-center py-3 px-2 text-sm rounded-lg"
                :class="{ 'bg-gray-200' : link.active, 'text-gray-200' : !link.url }"
            />
        </template>
    </nav>
</template>