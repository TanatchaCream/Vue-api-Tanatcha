<template>
    <div>
        <Navbar />
        <section class="projects">
            <h1 class="heading"> <span>my</span> projects </h1>
            <h3>{{project_name}}</h3>
            <p>{{project_detail}}</p>
            <div class="box-container">
                <iframe width="720" height="415" src="https://www.youtube.com/embed/MPV2METPeJU?start=2" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>
        </section>
    </div>
</template>

<script>
import Navbar from '../components/Navbar.vue';
export default {
    components: { Navbar },
    data() { 
        return { 
            project_name: 'Welcome to BBC EARTH! The world is an amazing place full of stories, beauty and natural wonder.',
            project_detail: '--- We ve collected the most precious moments from our beloved canine companions: from cute puppies opening their eyes for the first time, to loyal wild dogs and incredibly intelligent pets.---'
        }
     }
}
</script>

<style>

</style>