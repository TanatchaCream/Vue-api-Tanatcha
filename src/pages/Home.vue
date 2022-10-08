<template>
    <div>
        <Navbar />
        <section class="home">
            <div class="image">
                <img src="images/profile.png" alt="">
            </div>
            <div class="content">
                <h3>hi, i am {{name}}</h3>
                <span>{{motto}}</span>
                <p>{{content}}</p>
                <router-link to="/about" class="btn"> about me <i class="fas fa-user"></i> </router-link>
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
            name: 'Tanatcha Buratakan',
            motto: 'ทำวันนี้ให้ดีที่สุด',
            content: 'ปัจจุบันเป็นนักศึกษาชั้นปีที่2ในคณะวิศวกรรมศาสตร์สาขามัลติมีเดียและเอนเตอร์เทนเม้น มหาวิทยาลัยกรุงเทพ'
        }
     }
}
</script>

<style>

</style>