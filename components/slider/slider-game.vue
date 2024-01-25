<template>
  <section class="streamers__area section-pt-95 section-pb-90">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-lg-10 col-12">
          <div class="section__title text-center mb-60">
            <text-animation title="Our top streamers" />
            <h3 class="title">ลุ้นรับ Jackpot เงินล้านทุกยอดแทง</h3>
          </div>
        </div>
      </div>
      <Swiper v-bind="slider_setting" :modules="[Navigation, Pagination]" class="swiper-container streamers-active">
        <SwiperSlide v-for="item in streamers_data" :key="item.id">
          <div class="streamers__item">
            <div class="streamers__thumb">
              <nuxt-link to="/">
                <img :src="item.img" alt="img" />
              </nuxt-link>
            </div>
            <div class="streamers__content">
              <h4 class="name">{{ item.title }}</h4>
            </div>
          </div>
        </SwiperSlide>
      </Swiper>
      <div class="streamers__pagination">
        <div class="slider-button-prev streamers__pagination-arrow">
          <i class="fas fa-angle-left"></i>
        </div>
        <div class="swiper-pagination streamers__pagination-dots"></div>
        <div class="slider-button-next streamers__pagination-arrow">
          <i class="fas fa-angle-right"></i>
        </div>
      </div>
    </div>
  </section>
</template>
   
<script setup lang="ts">
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Pagination } from "swiper/modules";

// slider data
const streamers_data: {
  id: number;
  img: string;
  title: string;
}[] = [
    {
      id: 1,
      img: '/images/game/game-01.jpg',
      title: 'Joker Gaming'
    },
    {
      id: 2,
      img: '/images/game/game-02.jpg',
      title: 'SA Gaming'
    },
    {
      id: 3,
      img: '/images/game/game-01.jpg',
      title: 'Joker Gaming'
    },
    {
      id: 4,
      img: '/images/game/game-02.jpg',
      title: 'SA Gaming'
    },
    {
      id: 5,
      img: '/images/game/game-01.jpg',
      title: 'Joker Gaming'
    },
  ]

// slider setting
const slider_setting = {
  observer: true,
  observeParents: true,
  loop: false,
  slidesPerView: 5,
  spaceBetween: 20,
  breakpoints: {
    '1500': {
      slidesPerView: 5,
    },
    '1200': {
      slidesPerView: 4,
    },
    '992': {
      slidesPerView: 4,
    },
    '768': {
      slidesPerView: 3,
    },
    '576': {
      slidesPerView: 2,
    },
    '0': {
      slidesPerView: 1.5,
      centeredSlides: true,
      centeredSlidesBounds: true,
    },
  },
  pagination: {
    el: '.swiper-pagination',
    clickable: true,
  },
  navigation: {
    nextEl: ".slider-button-next",
    prevEl: ".slider-button-prev",
  }
};
</script>
