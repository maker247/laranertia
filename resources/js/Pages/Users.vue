<template>
    <Layout>
        <h1 class="text-4xl font-bold">Users</h1>

        <div class="mt-[400px]">
            <p>The current time is {{ time }}</p>

            <Link
                href="/users"
                class="text-blue-500"
                preserve-scroll
            >
                Refresh
            </Link>
        </div>
    </Layout>
</template>

<script>
import Layout from "../Shared/Layout"

export default {
    layout: Layout,

    props: {
        time: String
    }
}
</script>
