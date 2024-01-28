<template>
    <div class="w-[200px] transition-all bg-indigo-700 text-white py-4 px-2">
        <router-link
            :to="{ name: 'app.dashboard' }"
            class="flex items-center p-2 rounded transition-colors hover:bg-black/30"
        >
            <font-awesome-icon icon="fa-solid fa-house" size="xs" />
            <span class="text-xs ml-1"> Dashboard </span>
        </router-link>
        <router-link
            :to="{ name: 'app.products' }"
            class="flex items-center p-2 rounded transition-colors hover:bg-black/30"
        >
            <font-awesome-icon icon="fa-solid fa-list" size="xs" />
            <span class="text-xs ml-1"> Products </span>
        </router-link>
        <router-link
            :to="{ name: 'app.dashboard' }"
            class="flex items-center p-2 rounded transition-colors hover:bg-black/30"
        >
            <font-awesome-icon icon="fa-solid fa-user" size="xs" />
            <span class="text-xs ml-1"> Users </span>
        </router-link>
        <router-link
            :to="{ name: 'app.dashboard' }"
            class="flex items-center p-2 rounded transition-colors hover:bg-black/30"
        >
            <font-awesome-icon icon="fa-solid fa-chart-simple" size="xs" />
            <span class="text-xs ml-1"> Reports </span>
        </router-link>
    </div>
</template>

<script setup>
</script>

<style scoped></style>
