<template>
    <NuxtLayout name="admin">
        <div>
            <div
                class="border-b border-b-gray-900/10 lg:border-t lg:border-t-gray-900/5"
            >
                <dl
                    class="mx-auto grid max-w-7xl grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 lg:px-2 xl:px-0"
                >
                    <div
                        v-for="(stat, statIdx) in stats"
                        :key="stat.name"
                        :class="[
                            statIdx % 2 === 1
                                ? 'sm:border-l'
                                : statIdx === 2
                                ? 'lg:border-l'
                                : '',
                            'flex items-baseline flex-wrap justify-between gap-y-2 gap-x-4 border-t border-gray-900/5 px-4 py-10 sm:px-6 lg:border-t-0 xl:px-8',
                        ]"
                    >
                        <dt class="text-sm font-medium leading-6 text-gray-500">
                            {{ stat.name }}
                        </dt>
                        <dd
                            :class="[
                                stat.changeType === 'negative'
                                    ? 'text-rose-600'
                                    : 'text-gray-700',
                                'text-xs font-medium',
                            ]"
                        >
                            {{ stat.change }}
                        </dd>
                        <dd
                            class="w-full flex-none text-3xl font-medium leading-10 tracking-tight text-gray-900"
                        >
                            {{ stat.value }}
                        </dd>
                    </div>
                </dl>
            </div>
        </div>
        <div>
            <collectionstemplate />
        </div>
    </NuxtLayout>
</template>

<script setup>
const stats = [
    {
        name: "To Collect",
        value: "2",
        change: "+44.75%",
        changeType: "positive",
    },
    {
        name: "Total Collections",
        value: "$12,787.00",
        change: "+54.02%",
        changeType: "positive",
    },
    {
        name: "Total Outstanding Invoices",
        value: "$245,988.00",
        change: "-1.39%",
        changeType: "positive",
    },
    {
        name: "Total Expenses",
        value: "$30,156.00",
        change: "+10.18%",
        changeType: "negative",
    },
];
</script>
