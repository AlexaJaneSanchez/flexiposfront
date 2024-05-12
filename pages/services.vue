<template>
    <div>
        <NuxtLayout name="admin">
            <div class="mx-auto max-w-7xl px-6 lg:px-8 mb-10">
                <div class="mx-auto max-w-2xl text-center">
                    <h1
                        class="text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl"
                    >
                        Indulge in the delight of our service. Enjoy!
                    </h1>
                    <p class="mt-6 text-lg leading-8 text-gray-600">
                        Cultivate moments of bliss with our impeccable service.
                        Dive into a world of luxury and comfort, where every
                        detail is crafted with care to ensure your satisfaction.
                    </p>
                    <div class="mt-10 flex items-center justify-center gap-x-6">
                        <a
                            href="/"
                            class="rounded-md bg-indigo-600 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
                            >Home</a
                        >
                        <a
                            href="/contact"
                            class="text-sm font-semibold leading-6 text-gray-900"
                            >Contact Us <span aria-hidden="true">→</span></a
                        >
                    </div>
                </div>
            </div>
            <LazyServiceoffers />
        </NuxtLayout>
    </div>
</template>
