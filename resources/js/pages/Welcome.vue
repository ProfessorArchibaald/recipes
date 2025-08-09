<script setup lang="ts">
import { Head, Link } from '@inertiajs/vue3';
</script>

<template>
    <Head title="Welcome">
        <link rel="preconnect" href="https://rsms.me/" />
        <link rel="stylesheet" href="https://rsms.me/inter/inter.css" />
    </Head>

    <div class="min-h-screen flex flex-col items-center p-6 lg:justify-center lg:p-8" style="background-color: #800020;">
        <header class="mb-6 w-full max-w-[335px] text-sm lg:max-w-4xl">
            <nav class="flex items-center justify-end gap-4">
                <Link
                    v-if="$page.props.auth.user"
                    :href="route('dashboard')"
                    class="inline-block rounded-sm border px-5 py-1.5 text-sm text-white border-white hover:bg-white hover:text-[#800020]"
                >
                    Dashboard
                </Link>
                <template v-else>
                    <Link
                        :href="route('login')"
                        class="inline-block rounded-sm border px-5 py-1.5 text-sm text-white border-white hover:bg-white hover:text-[#800020]"
                    >
                        Log in
                    </Link>
                </template>
            </nav>
        </header>

        <div class="flex w-full items-center justify-center lg:grow">
            <main class="flex w-full max-w-[335px] lg:max-w-4xl overflow-hidden rounded-lg lg:flex-row">
                <!-- Picture Placeholder -->
                <div class="min-h-[300px] flex items-center justify-center w-full border border-dashed border-gray-200">
                    <span class="text-white">Picture Placeholder</span>
                </div>
            </main>
        </div>

        <div class="hidden h-14.5 lg:block"></div>
    </div>
</template>
