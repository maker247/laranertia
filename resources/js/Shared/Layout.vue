<template>
    <Head>
        <title>Layout</title>
        <meta
            type="description"
            content="Information for Layout my app"
            head-key="description"
        >
    </Head>

    <section class="p-6 bg-gray-200">
        <header class="flex justify-between">
            <div class="flex items-center">
                <h1 class="font-bold text-lg">
                    My App
                </h1>

                <p class="text-sm ml-4">
                    Welcome back, {{ username }}!
                </p>
            </div>

            <Nav />
        </header>
    </section>

    <section class="p-6 mx-auto max-w-3xl">
        <slot />
    </section>
</template>

<script setup>
import { computed } from "vue"
import { usePage } from "@inertiajs/inertia-vue3"
import Nav from "./Nav"

const username = computed(() => usePage().props.value.auth.user.username)

</script>
