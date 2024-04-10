<script setup>
    import { ref } from 'vue'

    let dropdownIsOpen = ref(false)

    const toggleDropdown = () => {
        dropdownIsOpen.value = !dropdownIsOpen.value
    }

    const featuresListItem = [
        {
            id: 1, name: 'History', link: '#',
        },
        {
            id: 2, name: 'Our Team', link: '#',
        },
        {
            id: 3, name: 'Blog', link: '#',
        }
    ]
</script>

<template>
    <li class="company" @:click="toggleDropdown">
        <p v-if="dropdownIsOpen">Company<img src="../../assets/icon/icon-arrow-up.svg" alt="Up Arrow" /></p>
        <p v-else>Company<img src="../../assets/icon/icon-arrow-down.svg" alt="Down Arrow" /></p>
        <div :class="`company__dropdown ${dropdownIsOpen?'show-company-dropdown':'hide-company-dropdown'}`">
            <ul class="company__dropdown-list">
                <li class="company__dropdown-list-item" v-for="listItem in featuresListItem" :key="listItem.id">
                    <a :href="listItem.link">{{ listItem.name }}</a>
                </li>
            </ul>
        </div>
    </li>
</template>