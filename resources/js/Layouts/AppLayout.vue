<script setup>
import { computed } from 'vue';
import { usePage } from '@inertiajs/vue3';
import { Link } from '@inertiajs/vue3';


</script>

<template>
    <main>
        <div class="hidden fixed top-0 right-0 px-6 py-4 sm:block">
            <div v-if="$page.props.auth.user" 
                    class="font-medium text-base text-gray-800">
                        {{ $page.props.auth.user.name }}
            </div>

            <template v-else>
                <Link :href="route('login')" class="text-sm text-gray-700 dark:text-gray-500 underline">Log in</Link>

                <Link
                    :href="route('register')"
                    class="ml-4 text-sm text-gray-700 dark:text-gray-500 underline"
                    >Register</Link
                >
            </template>
        </div>
        <content>
            <slot />
        </content>
    </main>
</template>