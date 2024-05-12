<template>
    <main class="pb-16 pt-8">
        <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
            <div class="px-4 sm:px-0">
                <h2 class="text-lg font-medium text-gray-900">Collections</h2>

                <!-- Tabs -->
                <div class="sm:hidden">
                    <label for="tabs" class="sr-only">Select a tab</label>
                    <!-- Use an "onChange" listener to redirect the user to the selected tab URL. -->
                    <select
                        id="tabs"
                        name="tabs"
                        class="mt-4 block w-full rounded-md border-0 py-1.5 pl-3 pr-10 ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-purple-500"
                    >
                        <option
                            v-for="tab in tabs"
                            :key="tab.name"
                            :selected="tab.current"
                        >
                            {{ tab.name }}
                        </option>
                    </select>
                </div>
                <div class="hidden sm:block">
                    <div class="border-b border-gray-200">
                        <nav
                            class="-mb-px mt-2 flex space-x-8"
                            aria-label="Tabs"
                        >
                            <a
                                v-for="tab in tabs"
                                :key="tab.name"
                                :href="tab.href"
                                :class="[
                                    tab.current
                                        ? 'border-purple-500 text-purple-600'
                                        : 'border-transparent text-gray-500 hover:border-gray-200 hover:text-gray-700',
                                    'whitespace-nowrap border-b-2 py-4 px-1 text-sm font-medium',
                                ]"
                            >
                                {{ tab.name }}
                                <span
                                    v-if="tab.count"
                                    :class="[
                                        tab.current
                                            ? 'bg-purple-100 text-purple-600'
                                            : 'bg-gray-100 text-gray-900',
                                        'ml-2 hidden rounded-full py-0.5 px-2.5 text-xs font-medium md:inline-block',
                                    ]"
                                    >{{ tab.count }}</span
                                >
                            </a>
                        </nav>
                    </div>
                </div>
            </div>

            <!-- Stacked list -->
            <ul
                role="list"
                class="mt-5 divide-y divide-gray-200 border-t border-gray-200 sm:mt-0 sm:border-t-0"
            >
                <li v-for="candidate in candidates" :key="candidate.email">
                    <a href="#" class="group block">
                        <div
                            class="flex items-center px-4 py-5 sm:px-0 sm:py-6"
                        >
                            <div class="flex min-w-0 flex-1 items-center">
                                <div class="flex-shrink-0">
                                    <img
                                        class="h-12 w-12 rounded-full group-hover:opacity-75"
                                        :src="candidate.imageUrl"
                                        alt=""
                                    />
                                </div>
                                <div
                                    class="min-w-0 flex-1 px-4 md:grid md:grid-cols-2 md:gap-4"
                                >
                                    <div>
                                        <p
                                            class="truncate text-sm font-medium text-purple-600"
                                        >
                                            {{ candidate.name }}
                                        </p>
                                        <p
                                            class="mt-2 flex items-center text-sm text-gray-500"
                                        >
                                            <EnvelopeIcon
                                                class="mr-1.5 h-5 w-5 flex-shrink-0 text-gray-400"
                                                aria-hidden="true"
                                            />
                                            <span class="truncate">{{
                                                candidate.email
                                            }}</span>
                                        </p>
                                    </div>
                                    <div class="hidden md:block">
                                        <div>
                                            <p class="text-sm text-gray-900">
                                                Paid On
                                                {{ " " }}
                                                <time
                                                    :datetime="
                                                        candidate.appliedDatetime
                                                    "
                                                    >{{
                                                        candidate.applied
                                                    }}</time
                                                >
                                            </p>
                                            <p
                                                class="mt-2 flex items-center text-sm text-gray-500"
                                            >
                                                <CheckCircleIcon
                                                    class="mr-1.5 h-5 w-5 flex-shrink-0 text-green-400"
                                                    aria-hidden="true"
                                                />
                                                {{ candidate.status }}
                                            </p>
                                            <p
                                                class="text-sm text-gray-900 mt-2"
                                            >
                                                Payed Amount:
                                                {{
                                                    " " +
                                                    candidate.paymentAmount +
                                                    "$"
                                                }}
                                            </p>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div>
                                <ChevronRightIcon
                                    class="h-5 w-5 text-gray-400 group-hover:text-gray-700"
                                    aria-hidden="true"
                                />
                            </div>
                        </div>
                    </a>
                </li>
            </ul>

            <!-- Pagination -->
            <nav
                class="flex items-center justify-between border-t border-gray-200 px-4 sm:px-0"
                aria-label="Pagination"
            >
                <div class="-mt-px flex w-0 flex-1">
                    <a
                        href="#"
                        class="inline-flex items-center border-t-2 border-transparent pr-1 pt-4 text-sm font-medium text-gray-500 hover:border-gray-200 hover:text-gray-700"
                    >
                        <ArrowLongLeftIcon
                            class="mr-3 h-5 w-5 text-gray-400"
                            aria-hidden="true"
                        />
                        Previous
                    </a>
                </div>
                <div class="hidden md:-mt-px md:flex">
                    <a
                        href="#"
                        class="inline-flex items-center border-t-2 border-purple-500 px-4 pt-4 text-sm font-medium text-purple-600"
                        aria-current="page"
                        >1</a
                    >
                    <!-- Current: "border-purple-500 text-purple-600", Default: "border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-200" -->
                    <a
                        href="#"
                        class="inline-flex items-center border-t-2 border-transparent px-4 pt-4 text-sm font-medium text-gray-500 hover:border-gray-200 hover:text-gray-700"
                        >2</a
                    >
                    <a
                        href="#"
                        class="inline-flex items-center border-t-2 border-transparent px-4 pt-4 text-sm font-medium text-gray-500 hover:border-gray-200 hover:text-gray-700"
                        >3</a
                    >
                    <a
                        href="#"
                        class="inline-flex items-center border-t-2 border-transparent px-4 pt-4 text-sm font-medium text-gray-500 hover:border-gray-200 hover:text-gray-700"
                        >4</a
                    >
                    <a
                        href="#"
                        class="inline-flex items-center border-t-2 border-transparent px-4 pt-4 text-sm font-medium text-gray-500 hover:border-gray-200 hover:text-gray-700"
                        >5</a
                    >
                    <a
                        href="#"
                        class="inline-flex items-center border-t-2 border-transparent px-4 pt-4 text-sm font-medium text-gray-500 hover:border-gray-200 hover:text-gray-700"
                        >6</a
                    >
                </div>
                <div class="-mt-px flex w-0 flex-1 justify-end">
                    <a
                        href="#"
                        class="inline-flex items-center border-t-2 border-transparent pl-1 pt-4 text-sm font-medium text-gray-500 hover:border-gray-200 hover:text-gray-700"
                    >
                        Next
                        <ArrowLongRightIcon
                            class="ml-3 h-5 w-5 text-gray-400"
                            aria-hidden="true"
                        />
                    </a>
                </div>
            </nav>
        </div>
    </main>
</template>

<script setup>
import { ref } from "vue";
import {
    Disclosure,
    DisclosureButton,
    DisclosurePanel,
    Listbox,
    ListboxButton,
    ListboxLabel,
    ListboxOption,
    ListboxOptions,
    Menu,
    MenuButton,
    MenuItem,
    MenuItems,
} from "@headlessui/vue";
import {
    ArrowLongLeftIcon,
    ArrowLongRightIcon,
    BriefcaseIcon,
    CalendarIcon,
    CheckCircleIcon,
    CheckIcon,
    ChevronDownIcon,
    ChevronRightIcon,
    CurrencyDollarIcon,
    EnvelopeIcon,
    LinkIcon,
    MagnifyingGlassIcon,
    MapPinIcon,
    PencilIcon,
} from "@heroicons/vue/20/solid";
import { Bars3Icon, BellIcon, XMarkIcon } from "@heroicons/vue/24/outline";

const tabs = [
    { name: "To Collect", href: "#", count: "2", current: false },
    { name: "Paid", href: "#", count: "4", current: true },
];
const candidates = [
    {
        name: "Emily Selman",
        email: "emily.selman@example.com",
        imageUrl:
            "https://images.unsplash.com/photo-1502685104226-ee32379fefbe?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80",
        applied: "January 7, 2020",
        appliedDatetime: "2020-07-01T15:34:56",
        paymentAmount: 150, // Amount in USD
        status: "Completed the payment via GCash.",
    },
    {
        name: "John Doe",
        email: "john.doe@example.com",
        imageUrl: "https://randomuser.me/api/portraits/men/1.jpg",
        applied: "March 15, 2020",
        appliedDatetime: "2020-03-15T12:45:00",
        paymentAmount: 200, // Amount in USD
        status: "Paid through PayPal.",
    },
    {
        name: "Alice Johnson",
        email: "alice.johnson@example.com",
        imageUrl: "https://randomuser.me/api/portraits/women/2.jpg",
        applied: "August 20, 2020",
        appliedDatetime: "2020-08-20T09:20:00",
        paymentAmount: 180, // Amount in USD
        status: "Transaction completed via credit card.",
    },
    {
        name: "Bob Smith",
        email: "bob.smith@example.com",
        imageUrl: "https://randomuser.me/api/portraits/men/3.jpg",
        applied: "November 3, 2020",
        appliedDatetime: "2020-11-03T17:55:00",
        paymentAmount: 220, // Amount in USD
        status: "Paid with cryptocurrency (Bitcoin).",
    },
];

const publishingOptions = [
    {
        name: "Published",
        description:
            "This job posting can be viewed by anyone who has the link.",
        current: true,
    },
    {
        name: "Draft",
        description: "This job posting will no longer be publicly accessible.",
        current: false,
    },
];

const selected = ref(publishingOptions[0]);
</script>
