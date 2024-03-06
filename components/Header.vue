<template>
    <header class="shadow-sm bg-white">
        <nav class="container mx-auto p-4 flex justify-between">
            <ul class="flex">
                <li class="p-2"><NuxtLink to="/">Home</NuxtLink></li>
                <li class="p-2"><NuxtLink to="/about">About</NuxtLink></li>
                <li class="p-2"><NuxtLink to="/employee">Employee</NuxtLink></li>
            </ul>
        </nav>
    </header>
</template>

<style scroped>
    .router-link-active {
        color: lightcoral
    }
</style>