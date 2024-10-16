<template>
    <Head>
        <title>Users</title>
        <meta
            type="description"
            content="Information for Users my app"
            head-key="description"
        >
    </Head>

    <div class="flex justify-between">
        <div class="flex items-center space-x-2">
            <h1 class="text-4xl font-bold">Users</h1>

            <Link
                href="/users/create"
                class="text-blue-500 text-sm"
            >
                Create
            </Link>
        </div>

        <input
            v-model="search"
            type="text"
            class="border px-2 rounded"
            placeholder="Search"
        >
    </div>

    <div class="mt-8">
        <table class="table-auto w-full">
            <tbody>
                <tr v-for="user in users.data" :key="user.id">
                    <td>{{ user.name }}</td>
                    <td><Link href="/">Edit</Link></td>
                </tr>
            </tbody>
        </table>

<!--        paginator-->
        <div class="mt-6">
            <Pagination
                :links="users.links"
            />
        </div>
    </div>
</template>

<script setup>
import {
    ref,
    watch
} from "vue"
import { Inertia } from "@inertiajs/inertia"
import Pagination from "../../Shared/Pagination"
import debounce from "lodash/debounce"

let props = defineProps({
    users: Object,
    filters: Object
})

let search = ref(props.filters.search)

watch(search, debounce(function (value) {
    Inertia.get(
        '/users',
        {
            search: value
        },
        {
            preserveState: true,
            replace: true
        }
    )
}, 500))

</script>
