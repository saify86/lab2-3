<script setup>

import { Swiper, SwiperSlide } from 'swiper/vue';
import { Pagination} from 'swiper/modules';
import '@/../node_modules/swiper/swiper-bundle.min.css';

const cards = [
    {
        src: "/chat_logo.svg",
        title: "Общение с классом",
        text: "Видеосвязь<br>Чат с классом",
        color: "opportunities__card-blue"
    },

    {
        src: "/monitor_logo.svg",
        title: "Проведение занятий",
        text: "Презентация файлов <br> Демонстрация экрана",
        color: "opportunities__card-orange"
    },

    {
        src: "/menu_logo.svg",
        title: "Посещаемость",
        text: "Автоматическое <br>отслеживание<br> присутствующих",
        color: "opportunities__card-blue"
    },

    {
        src: "/reload_logo.svg",
        title: "История занятий",
        text: "Материалы урока",
        color: "opportunities__card-orange"
    }
]

</script>

<template>
    <section class="opportunities">
        <div class="container">
            <div class="opportunities__header">
                <h3>Возможности</h3>
            </div>
            <swiper :modules="[Pagination]" :space-between="30"  :pagination="{ el: '.opportunities__swiper-pagination',clickable: true }"
                :breakpoints="{
                0: { slidesPerView: 1 },
                560: { slidesPerView: 2 },
                992: { slidesPerView: 3 },
                1200: { slidesPerView: 4 }
            }" 
                >

                <swiper-slide v-for="(item,index) in cards" :key="index">
                    <div class="opportunities__swiper-slide">
                        <div class="opportunities__card" :class="item.color">
                            <img :src="item.src" alt="" class="opportunities__logo">
                            <h4>{{item.title}}</h4>
                            <p v-html="item.text"></p>
                        </div>
                    </div>
                </swiper-slide>
                <div class="opportunities__swiper-pagination swiper-pagination"></div>
            </swiper>
        </div>
    </section>
</template>

<style scoped>

</style>