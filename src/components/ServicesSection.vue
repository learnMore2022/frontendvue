<template >
    <section class="text-white mt-20" id="services">
        <div class="px-4 xl:pl-16">
            <h2 class="text-4xl font-bold text-white mb-4">My Services</h2>
        </div>
        <div class="py-8 xl:px-16 px-4 sm:py-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3">
            <div v-for="service in services" :key="service.id" data-aos="fade-up"
            class="px-8 py-12 rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641]"
            >
                <div class="mx-auto h-24 w-24 text-center xl:h-28 xl:w-28">
                    <div>
                        <img :src="service.icon" alt="service icon">
                    </div>
                </div>
                <div class="text-center">
                    <h3 class="pt-8 text-lg font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary lg:text-xl">
                        {{ service.name }}
                    </h3>
                    <p class="text-grey pt-4 text-sm group-hover:text-white md:text-base">
                        {{ service.description }}
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>
<script setup>
import {ref} from 'vue';
const services =ref([
    {
        id:1,
        icon:'https://img.icons8.com/ios-filled/100/ffffff/google-code.png',
        name:'WEB DEVELOPMENT',
        description:'I offer professional web development services to help you create sophisticated, reliable, and user-friendly websites and applications. Whether you need a simple landing page or a complex web application, I have the skills and experience to bring your vision to life. Let's connect and discuss how we can build an exceptional online presence for you!!'
    },
    {
        id:2,
        icon:'https://img.icons8.com/external-vectorslab-glyph-vectorslab/100/fffeee/external-Technical-Writing-mobile-app-development-vectorslab-glyph-vectorslab.png',
        name:'Technical Writing',
        description:'I provide expert technical writing services to help you create clear, concise, and comprehensive documentation. Whether you need user manuals, API documentation, or technical guides, I have the expertise to deliver high-quality content that meets your needs. Let's connect and discuss how we can enhance your technical documentation!!'
    },
    {
        id:3,
        icon:'https://img.icons8.com/external-solid-design-circle/100/ffffff/external-Mobile-Development-digital-marketing-solid-design-circle.png',
        name:'Mobile Development',
        description:'I offer comprehensive mobile development services to help you create high-quality, reliable, and user-friendly mobile applications. Whether you need an app for iOS, Android, or both, I have the expertise to deliver a seamless and engaging user experience. Let's connect and discuss how we can bring your mobile app ideas to life!'
    },
    {
        id:4,
        icon:'https://img.icons8.com/ios-filled/100/ffffff/email-open.png',
        name:'WEB DEVELOPMENT',
        description:' I offer professional web development services to help you create sophisticated, reliable, and user-friendly websites and applications. Whether you need a simple landing page or a complex web application, I have the skills and experience to bring your vision to life. Let's connect and discuss how we can build an exceptional online presence for you!'
    },
    ])
</script>

