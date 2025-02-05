<template >
    <section class="text-white mt-20" id="testimonials" data-aos="zoom-in">
        <h2 class="text-4xl font-bold text-white text-left mb-4 px-4 xl:pl-16">Testimonials</h2>
        <div class="px-4 xl:px-16">
            <Carousel v-bind="settings" :breakpoints="breakpoints" >
                <Slide v-for="element in testimonials" :key="element.id">
                    <div class="carousel__item p-4">
                        <div class="w-full mx-auto bg-[#111a3e] shadow-lg border border-[#1f1641] p-5 text-white font-light mb-6">
                            <div class="w-full flex mb-4 items-center">
                                <div class="overflow-hidden rounded-full w-10 h-10 bg-gray-50 border border-gray-200">
                                    <img :src="element.image" alt="testimonial image" loading="lazy">
                                </div>
                                <h6 class="ml-4 font-bold text-sm uppercase text-white">{{ element.fullName }}</h6>
                            </div>
                            <div class="w-full">
                                <p class="text-sm leading-tight">
                                    <span class="text-lg leading-none italic font-bold text-white mr-1">"</span>
                                        {{ element.comment }}
                                    <span class="text-lg leading-none italic font-bold text-white mr-1">"</span>
                                </p>
                            </div>
                        </div>
                    </div>
                </Slide> 
                <template #addons>
                    <Navigation />
                </template>
            </Carousel>
        </div>
    </section>
</template>
<script setup>
import { ref } from 'vue';
import { Carousel , Navigation , Slide } from 'vue3-carousel';
import 'vue3-carousel/dist/carousel.css';
//Carousel settings
const settings =ref({
    itemsToShow:1,
    snapAlign:"center",
})

//Breakpoints
const breakpoints =ref({
    700:{
        itemsToShow:2.5,
        snapAlign:'center',
    },
    1024:{
        itemsToShow:3,
        snapAlign:'start'
    }
})

const testimonials=ref([
    {
        id:1,
        fullName:'sharvil kumar singh',
        image:'src/assets/image.png',
        comment:'Working with Sourabh was an absolute pleasure. His expertise in web development is unparalleled, and he delivered a website that exceeded our expectations. The project was completed on time and within budget, and the final product is both visually stunning and highly functional. I highly recommend Sourabh for any web development needs!'
    },
    {
        id:2,
        fullName:'sonam onkarnath tripathi',
        image:'src/assets/image.png',
        comment:'Sourabh's mobile development skills are top-notch. He transformed our app concept into a fully functional and visually appealing product. The entire process was smooth, and Sourabh was always available to address our concerns and provide valuable insights. Our app has received fantastic feedback from users, and we couldn't be happier with the results. Highly recommend Sourabh for any mobile development projects'
    },
    {
        id:3,
        fullName:'sukriti singh',
        image:'src/assets/image.png',
        comment:'Sourabh's technical writing skills are exceptional. He took complex technical concepts and translated them into easy-to-understand documentation that our users love. His attention to detail and ability to communicate effectively made a significant impact on our project's success. I highly recommend Sourabh for any technical writing needs!'
    },
   
])
</script>
<style >
    .carousel__prev,.carousel__next {
        color: white !important;
    }
</style>
