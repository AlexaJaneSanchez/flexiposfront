<template>
    <div class="px-4 sm:px-6 lg:px-8">
        <div class="sm:flex sm:items-center">
            <div class="sm:flex-auto">
                <h1 class="text-base font-semibold leading-6 text-gray-900">
                    Bills
                </h1>
                <p class="mt-2 text-sm text-gray-700">
                    Effortless bill management, simplified.
                </p>
            </div>
            <div class="mt-4 sm:ml-16 sm:mt-0 sm:flex-none">
                <button
                    type="button"
                    class="block rounded-md bg-indigo-600 px-3 py-2 text-center text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
                >
                    Export
                </button>
            </div>
        </div>
        <div class="mt-8 flow-root">
            <div class="-mx-4 -my-2 overflow-x-auto sm:-mx-6 lg:-mx-8">
                <div
                    class="inline-block min-w-full py-2 align-middle sm:px-6 lg:px-8"
                >
                    <table class="min-w-full divide-y divide-gray-300">
                        <thead>
                            <tr>
                                <th
                                    scope="col"
                                    class="whitespace-nowrap py-3.5 pl-4 pr-3 text-left text-sm font-semibold text-gray-900 sm:pl-0"
                                >
                                    Transaction ID
                                </th>
                                <th
                                    scope="col"
                                    class="whitespace-nowrap px-2 py-3.5 text-left text-sm font-semibold text-gray-900"
                                >
                                    Company
                                </th>
                                <th
                                    scope="col"
                                    class="whitespace-nowrap px-2 py-3.5 text-left text-sm font-semibold text-gray-900"
                                >
                                    Share
                                </th>
                                <th
                                    scope="col"
                                    class="whitespace-nowrap px-2 py-3.5 text-left text-sm font-semibold text-gray-900"
                                >
                                    Commision
                                </th>
                                <th
                                    scope="col"
                                    class="whitespace-nowrap px-2 py-3.5 text-left text-sm font-semibold text-gray-900"
                                >
                                    Price
                                </th>
                                <th
                                    scope="col"
                                    class="whitespace-nowrap px-2 py-3.5 text-left text-sm font-semibold text-gray-900"
                                >
                                    Quantity
                                </th>
                                <th
                                    scope="col"
                                    class="whitespace-nowrap px-2 py-3.5 text-left text-sm font-semibold text-gray-900"
                                >
                                    Net amount
                                </th>
                                <th
                                    scope="col"
                                    class="relative whitespace-nowrap py-3.5 pl-3 pr-4 sm:pr-0"
                                >
                                    <span class="sr-only">Edit</span>
                                </th>
                            </tr>
                        </thead>
                        <tbody class="divide-y divide-gray-200 bg-white">
                            <tr
                                v-for="transaction in transactions"
                                :key="transaction.id"
                            >
                                <td
                                    class="whitespace-nowrap py-2 pl-4 pr-3 text-sm text-gray-500 sm:pl-0"
                                >
                                    {{ transaction.id }}
                                </td>
                                <td
                                    class="whitespace-nowrap px-2 py-2 text-sm font-medium text-gray-900"
                                >
                                    {{ transaction.company }}
                                </td>
                                <td
                                    class="whitespace-nowrap px-2 py-2 text-sm text-gray-900"
                                >
                                    {{ transaction.share }}
                                </td>
                                <td
                                    class="whitespace-nowrap px-2 py-2 text-sm text-gray-500"
                                >
                                    {{ transaction.commission }}
                                </td>
                                <td
                                    class="whitespace-nowrap px-2 py-2 text-sm text-gray-500"
                                >
                                    {{ transaction.price }}
                                </td>
                                <td
                                    class="whitespace-nowrap px-2 py-2 text-sm text-gray-500"
                                >
                                    {{ transaction.quantity }}
                                </td>
                                <td
                                    class="whitespace-nowrap px-2 py-2 text-sm text-gray-500"
                                >
                                    {{ transaction.netAmount }}
                                </td>
                                <td
                                    class="relative whitespace-nowrap py-2 pl-3 pr-4 text-right text-sm font-medium sm:pr-0"
                                >
                                    <a
                                        href="#"
                                        class="text-indigo-600 hover:text-indigo-900"
                                        >Edit<span class="sr-only"
                                            >, {{ transaction.id }}</span
                                        ></a
                                    >
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const transactions = [
    {
        id: "AAPS0L",
        company: "Chase & Co.",
        share: "CAC",
        commission: "+$4.37",
        price: "$3,509.00",
        quantity: "12.00",
        netAmount: "$4,397.00",
    },
    {
        id: "BDSF2P",
        company: "Global Tech",
        share: "GLT",
        commission: "-$6.12",
        price: "$1,920.00",
        quantity: "10.00",
        netAmount: "$1,914.00",
    },
    {
        id: "CJJK9R",
        company: "Farmers Group",
        share: "FAR",
        commission: "+$3.25",
        price: "$2,150.00",
        quantity: "15.00",
        netAmount: "$32,275.00",
    },
    {
        id: "DHRF8S",
        company: "Tech Solutions Inc.",
        share: "TSI",
        commission: "-$8.20",
        price: "$5,900.00",
        quantity: "5.00",
        netAmount: "$29,460.00",
    },
    {
        id: "EKLO4M",
        company: "Energy Corp.",
        share: "ENC",
        commission: "+$2.50",
        price: "$890.00",
        quantity: "20.00",
        netAmount: "$17,800.00",
    },
    {
        id: "FTYL3N",
        company: "Fashion Trends Ltd.",
        share: "FTL",
        commission: "-$3.75",
        price: "$1,320.00",
        quantity: "8.00",
        netAmount: "$10,488.00",
    },
    {
        id: "GDMH7O",
        company: "Healthcare Inc.",
        share: "HCI",
        commission: "+$1.80",
        price: "$3,200.00",
        quantity: "10.00",
        netAmount: "$32,018.00",
    },
    {
        id: "HKUI5T",
        company: "Eco-Friendly Corp.",
        share: "EFC",
        commission: "-$5.50",
        price: "$2,750.00",
        quantity: "6.00",
        netAmount: "$16,445.00",
    },
    {
        id: "IDWF6U",
        company: "Food Services Group",
        share: "FSG",
        commission: "+$2.90",
        price: "$1,410.00",
        quantity: "12.00",
        netAmount: "$16,920.00",
    },
    {
        id: "JYRG2V",
        company: "Transport Solutions Ltd.",
        share: "TSL",
        commission: "-$4.10",
        price: "$2,300.00",
        quantity: "9.00",
        netAmount: "$20,390.00",
    },
    {
        id: "KPQA1W",
        company: "Real Estate Holdings",
        share: "REH",
        commission: "+$7.20",
        price: "$4,800.00",
        quantity: "7.00",
        netAmount: "$33,624.00",
    },
    {
        id: "LSDT5X",
        company: "Media Group Inc.",
        share: "MGI",
        commission: "-$6.75",
        price: "$1,625.00",
        quantity: "5.00",
        netAmount: "$8,087.00",
    },
    {
        id: "MQWB3Y",
        company: "Education Solutions",
        share: "EDS",
        commission: "+$3.40",
        price: "$2,200.00",
        quantity: "10.00",
        netAmount: "$22,203.00",
    },
    {
        id: "NRTG4Z",
        company: "Software Innovations",
        share: "SFI",
        commission: "-$4.85",
        price: "$3,950.00",
        quantity: "4.00",
        netAmount: "$15,754.00",
    },
    {
        id: "OPSU1A",
        company: "Construction Holdings",
        share: "CHO",
        commission: "+$6.60",
        price: "$4,200.00",
        quantity: "5.00",
        netAmount: "$21,006.00",
    },
    {
        id: "PTVW9B",
        company: "Retail Ventures Ltd.",
        share: "RVL",
        commission: "-$2.25",
        price: "$1,150.00",
        quantity: "8.00",
        netAmount: "$9,000.00",
    },
];
</script>
