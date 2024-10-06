<script setup>
import { faker } from '@faker-js/faker'
const fullname = faker.person.fullName()
const firstname = faker.person.firstName()
const lastname = faker.person.lastName()
const job_title = faker.person.jobTitle()
const bio = faker.lorem.lines(2)
const username = faker.internet.userName({firstName: firstname, lastName:lastname}).toLowerCase()

</script>

<template>
<!-- {{ fullname }} <br /> -->
<div class="border border-gray-400 rounded-lg shadow bg-gray-200 h-full">
    <img :src="faker.image.urlLoremFlickr({width: 640, height: 480, category: 'beaches'})" />
    <div class="p-4">
        <p class="mb-2 text-3xl font-bold">{{ fullname }}</p>
        <p class="mb-4 font-semibold text-gray-700">{{ job_title }}</p>
        <p class="mb-4 font-medium text-gray-700">{{ bio }}</p>
    </div>
</div>
</template>