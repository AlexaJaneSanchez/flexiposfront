<template>
    <div>
        <NuxtLayout name="admin">
            <Userstable />
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8 pt-16 pb-28">
                <!-- Content goes here -->
                <eventscalendar />
                <Salesummary />
            </div>
        </NuxtLayout>
    </div>
</template>

<script setup>
import { ref } from "vue";
import {
    Dialog,
    DialogPanel,
    Menu,
    MenuButton,
    MenuItem,
    MenuItems,
} from "@headlessui/vue";
import {
    ArrowDownCircleIcon,
    ArrowPathIcon,
    ArrowUpCircleIcon,
    Bars3Icon,
    EllipsisHorizontalIcon,
    PlusSmallIcon,
} from "@heroicons/vue/20/solid";
import { BellIcon, XMarkIcon } from "@heroicons/vue/24/outline";

const navigation = [
    { name: "Home", href: "#" },
    { name: "Invoices", href: "#" },
    { name: "Clients", href: "#" },
    { name: "Expenses", href: "#" },
];
const secondaryNavigation = [
    { name: "Last 7 days", href: "#", current: true },
    { name: "Last 30 days", href: "#", current: false },
    { name: "All-time", href: "#", current: false },
];
const stats = [
    {
        name: "Revenue",
        value: "$405,091.00",
        change: "+4.75%",
        changeType: "positive",
    },
    {
        name: "Overdue invoices",
        value: "$12,787.00",
        change: "+54.02%",
        changeType: "negative",
    },
    {
        name: "Outstanding invoices",
        value: "$245,988.00",
        change: "-1.39%",
        changeType: "positive",
    },
    {
        name: "Expenses",
        value: "$30,156.00",
        change: "+10.18%",
        changeType: "negative",
    },
];
const statuses = {
    Paid: "text-green-700 bg-green-50 ring-green-600/20",
    Withdraw: "text-gray-600 bg-gray-50 ring-gray-500/10",
    Overdue: "text-red-700 bg-red-50 ring-red-600/10",
};
const days = [
    {
        date: "Today",
        dateTime: "2023-03-22",
        transactions: [
            {
                id: 1,
                invoiceNumber: "00012",
                href: "#",
                amount: "$7,600.00 USD",
                tax: "$500.00",
                status: "Paid",
                client: "Reform",
                description: "Website redesign",
                icon: ArrowUpCircleIcon,
            },
            {
                id: 2,
                invoiceNumber: "00011",
                href: "#",
                amount: "$10,000.00 USD",
                status: "Withdraw",
                client: "Tom Cook",
                description: "Salary",
                icon: ArrowDownCircleIcon,
            },
            {
                id: 3,
                invoiceNumber: "00009",
                href: "#",
                amount: "$2,000.00 USD",
                tax: "$130.00",
                status: "Overdue",
                client: "Tuple",
                description: "Logo design",
                icon: ArrowPathIcon,
            },
        ],
    },
    {
        date: "Yesterday",
        dateTime: "2023-03-21",
        transactions: [
            {
                id: 4,
                invoiceNumber: "00010",
                href: "#",
                amount: "$14,000.00 USD",
                tax: "$900.00",
                status: "Paid",
                client: "SavvyCal",
                description: "Website redesign",
                icon: ArrowUpCircleIcon,
            },
        ],
    },
];
const clients = [
    {
        id: 1,
        name: "Tuple",
        imageUrl: "https://tailwindui.com/img/logos/48x48/tuple.svg",
        lastInvoice: {
            date: "December 13, 2022",
            dateTime: "2022-12-13",
            amount: "$2,000.00",
            status: "Overdue",
        },
    },
    {
        id: 2,
        name: "SavvyCal",
        imageUrl: "https://tailwindui.com/img/logos/48x48/savvycal.svg",
        lastInvoice: {
            date: "January 22, 2023",
            dateTime: "2023-01-22",
            amount: "$14,000.00",
            status: "Paid",
        },
    },
    {
        id: 3,
        name: "Reform",
        imageUrl: "https://tailwindui.com/img/logos/48x48/reform.svg",
        lastInvoice: {
            date: "January 23, 2023",
            dateTime: "2023-01-23",
            amount: "$7,600.00",
            status: "Paid",
        },
    },
];

const mobileMenuOpen = ref(false);
</script>
