<script setup>

    import DatabizLogo from '../../assets/images/client-databiz.svg'
    import AudiophileLogo from '../../assets/images/client-audiophile.svg'
    import MeetLogo from '../../assets/images/client-meet.svg'
    import MakerLogo from '../../assets/images/client-maker.svg'

    const clientList = [
        {
        id: 1, img: DatabizLogo, alt: 'Databiz Logo',
        },
        {
        id: 2, img: AudiophileLogo, alt: 'Audiophile Logo',
        },
        {
        id: 3, img: MeetLogo, alt: 'Meet Logo',
        },
        {
        id: 4, img: MakerLogo, alt: 'Maker Logo',
        },
    ]
</script>

<template>
    <ul class="client-list">
      <li v-for="client in clientList">
        <img :src="client.img" :alt="client.alt" :key="client.id"/>
      </li>
    </ul>
</template>