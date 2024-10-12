<template>
    <h1 class="text-4xl font-bold">Home</h1>

    <Nav />

    <div class="mt-[400px]">
        <p>The current time is {{ time }}</p>

        <Link
            href="/"
            class="text-blue-500"
            preserve-scroll
        >Refresh</Link>
    </div>
</template>

<script>
import Nav from '../Shared/Nav'
import { Link } from "@inertiajs/inertia-vue3"

export default {
    components: {
        Nav,
        Link
    },
    props: {
        time: String
    }
}
</script>
