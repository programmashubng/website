<template>
    <section class="our_event_section mt-[50px] md:mt-[100px] px-5 py-[60px] md:py-[100px]" id="our-events">
        <div class=" our_event_container container mx-auto">
            <div class="our_event_heading_area">
                <div class="our_event_heading_left mb-[20px]">
                    <div class="top_line"></div>
                    <h2 class="our_event text-[32px] md:text-[40px]">Our Events</h2>
                    <h4 class="our_event_subtitle">STAY UP TO DATE WITH ALL OUR EVENTS</h4>
                </div>
                <div class="our_event_heading_right hidden md:flex">
                    <img src="@/assets/images/icons/left-arrow.png" alt="left-arrow" @click="prev()" />
                    <img src="@/assets/images/icons/right-arrow.png" alt="right-arrow"  @click="next()" />
                </div>
            </div>
            <div class="our_event_content_are">
                <Carousel ref="carousel"  :settings="settings" :breakpoints="breakpoints" :autoplay="2000" :wrap-around="true">
                    <slide v-for="event in allEvents" :key="event">
                        <div class="single_event">
                            <nuxt-img src="https://res.cloudinary.com/haayzeed/image/upload/q_auto/v1669585925/programmers-hub-team/team/group.png" :alt="event.event_name" loading="lazy" />
                            <div class="single_event_desc">
                                <h1 class="single_event_date text-left">{{event.event_date}} </h1>
                                <h2 class="single_event_name text-left">{{event.event_name}}
                                </h2>
                            </div>
                        </div>
                    </slide>
                </Carousel>
            </div>
        </div>
    </section>
</template>
<script>
import { Carousel, Navigation, Slide, Pagination  } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'

export default {
    components: {
        Carousel,
        Slide,
        Navigation,
        Pagination 
    },
    data: () => ({
        settings: {
            itemsToShow: 3,
            snapAlign: 'start',
        },
        allEvents: [
            {
                'event_date': '20TH NOVEMBER, 2022',
                'event_name': 'SOFTWARE DESIGN & DEVELOPMENT DAY DEVELOPMENT DAY',
                'eventImage': 'group.png'
            },
            {
                'event_date': '2TH december, 2022',
                'event_name': 'SOFTWARE DESIGN & DEVELOPMENT DAY DEVELOPMENT DAY',
                'eventImage': 'group.png'
            },
            {
                'event_date': '14TH january, 2023',
                'event_name': 'SOFTWARE DESIGN & DEVELOPMENT DAY DEVELOPMENT DAY',
                'eventImage': 'group.png'
            },
            {
                'event_date': '40TH jabuary, 2023',
                'event_name': 'SOFTWARE DESIGN & DEVELOPMENT DAY DEVELOPMENT DAY',
                'eventImage': 'group.png'
            },
            {
                'event_date': '28TH march, 2023',
                'event_name': 'SOFTWARE DESIGN & DEVELOPMENT DAY DEVELOPMENT DAY',
                'eventImage': 'group.png'
            },
            {
                'event_date': '4TH april, 2023',
                'event_name': 'SOFTWARE DESIGN & DEVELOPMENT DAY DEVELOPMENT DAY',
                'eventImage': 'group.png'
            },
        ],        
        breakpoints: {
            // 700px and up
            360: {
                itemsToShow: 1,
                snapAlign: 'center',
            },
            600: {
                itemsToShow: 2,
                snapAlign: 'center',
            },
            // 1024 and up
            1024: {
                itemsToShow: 3,
                snapAlign: 'center',
            },
        },
    }),
    methods: {
    next() {
      this.$refs.carousel.next()
    },
    prev() {
      this.$refs.carousel.prev()
    },
  }
}
</script>