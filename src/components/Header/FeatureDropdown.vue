<script setup>
    import { ref } from 'vue'
    import todoIcon from '../../assets/icon/icon-todo.svg'
    import calendarIcon from '../../assets/icon/icon-calendar.svg'
    import reminderIcon from '../../assets/icon/icon-reminders.svg'
    import planningIcon from '../../assets/icon/icon-planning.svg'

    let dropdownIsOpen = ref(false)

    const toggleDropdown = () => {
        dropdownIsOpen.value = !dropdownIsOpen.value
    }

    const featuresListItem = [
        {
            id: 1, name: 'Todo List', img: todoIcon, alt: 'Note', link: '#',
        },
        {
            id: 2, name: 'Calendar', img: calendarIcon, alt: 'Calendar', link: '#',
        },
        {
            id: 3, name: 'Reminders', img: reminderIcon, alt: 'Bell', link: '#',
        },
        {
            id: 4, name: 'Planning', img: planningIcon, alt: 'Clock', link: '#',
        },
    ]
</script>
<template>
    <li class="features" @:click="toggleDropdown">
        <p v-if="dropdownIsOpen">Features<img src="../../assets/icon/icon-arrow-up.svg" alt="Up Arrow" /></p>
        <p v-else>Features<img src="../../assets/icon/icon-arrow-down.svg" alt="Down Arrow" /></p>
        <div :class="`features__dropdown ${dropdownIsOpen?'show-features-dropdown':'hide-features-dropdown'}`">
            <ul class="features__dropdown-list">
                <li class="features__dropdown-list-item" v-for="listItem in featuresListItem" :key="listItem.id">
                    <a :href="listItem.link"><img :src="listItem.img" :alt="listItem.alt" />{{ listItem.name }}</a>
                </li>
            </ul>
        </div>
    </li>
</template>