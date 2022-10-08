<template>
    <div>
        <Navbar />

        <section class="about">

            <h1 class="heading"> about <span>me</span> </h1>

            <div class="row">

                <div class="info-container">

                    <h1>personal info</h1>

                    <div class="box-container">

                        <div class="box">
                            <h3> <span>name : </span> {{name}} </h3>
                            <h3> <span>age : </span> {{age}} </h3>
                            <h3> <span>email : </span> {{email}} </h3>
                            <h3> <span>address : </span> {{address}} </h3>
                        </div>

                        <div class="box">
                            <h3> <span>student : </span> {{student}} </h3>
                            <h3> <span>skill : </span> {{skill}} </h3>
                            <h3> <span>experience : </span> {{experience}} </h3>
                            <h3> <span>language : </span> {{language}} </h3>
                        </div>

                    </div>

                    <a href="/profilewithcss/files/resume.pdf" class="btn"> download CV <i class="fas fa-download"></i>
                    </a>

                </div>

                <div class="count-container">

                    <div class="box" v-for="e in Freetime" :key="e.hobby">
                        <h3>{{e.hobby}}</h3>
                        <p>{{e.ex}}</p>
                    </div>
                </div>

            </div>

        </section>

        <!-- about section ends -->

        <!-- skills section starts  -->

        <section class="skills">

            <h1 class="heading"> <span>my</span> skills </h1>

            <div class="box-container" v-for="e in skills" :key="e.name">
                <div class="box">
                    <h3>{{e.name}}</h3>
                </div>
            </div>

        </section>

        <!-- skills section ends -->

        <!-- education section starts  -->

        <section class="education">

            <h1 class="heading"> <span>my</span> experience </h1>

            <div class="box-container">

                <div class="box" v-for="e in study" :key="e.years">
                    <i class="fas fa-briefcase"></i>
                    <span>{{e.years}}</span>
                    <h3>{{e.school}}</h3>
                    <p>{{e.jobs}}</p>
                </div>
            </div>

        </section>
    </div>
</template>

<script>
import Navbar from "../components/Navbar.vue";
import axios from 'axios'

export default {
    components: { Navbar },
    methods: {
        async fetchExperience() {
            try {
                let res = await axios.get("https://633fc566e44b83bc73c0f545.mockapi.io/profile/v1/experiences")
                this.study = res.data
            } catch (error) {

            }
        }, async fetchSkill() {
            try {
                let res = await axios.get("https://633fc566e44b83bc73c0f545.mockapi.io/profile/v1/skills")
                this.skills = res.data
            } catch (error) {

            }
        }
    },
    data() {
        return {
            name: 'Tanatcha Buratakan',
            age: '19',
            email: 'kann0806@gmail.com',
            address: 'Ranong, Thailand 85110',
            student: 'Current',
            skill: 'เล่นดนตรี(ขิม),วาดรูป',
            experience: '15',
            language: 'Thai,English.Chinese',

            study: [],

            Freetime: [{
                hobby: 'Read Novel',
                ex: 'Fantasy,Love comady'
            }, {
                hobby: 'Drawing',
                ex: 'สีน้ำ,สีชอล์ก,ดิจิดอลอาร์ท'
            }, {
                hobby: 'ดูหนัง',
                ex: 'Netflix,Hbo go'
            }, {
                hobby: 'Listening to music',
                ex: 'Sptify,Youtube'
            }],

            skiller: [{
                sk: 'เล่นดนตรี ขิม'
            }, {
                sk: 'Drawing'
            }, {
                sk: 'ร้องเพลง'
            }, {
                sk: 'เต้น'
            }, {
                sk: 'แต่งหน้า'
            }
            ],
            skills: []
        }
    },

    beforeMount() {
        this.fetchExperience()
        this.fetchSkill()
    }

}
</script>

<style>

</style>