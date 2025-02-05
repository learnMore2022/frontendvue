<template>
    <section class="text-white mt-18" id="skills">
        <div class="absolute right-0 top-[110rem] h-full w-full justify-end">
            <span class="flex opacity-20">
                <span class="w-16 h-32 rounded-l-full flex bg-primary blur-2xl"></span>
                <span class="w-16 h-32 rounded-r-full flex bg-[#f88fc2] blur-2xl mt-14"></span>
            </span>
        </div>
        <div class="md:grid md:grid-cols-2 gap-8 items-center py-8 px-4 xl:gap-16 xl:px-16">
            <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full w-[80%]">
                <h2 class="text-4xl font-bold text-white text-left mb-4">My 
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Skills</span>
                </h2>
                <div class="mt-8" v-for="skill in skills" :key="skill.id">
                    <div class="flex items-end justify-between" data-aos="fade-right">
                        <h4 class="font-semibold uppercase text-white">
                            {{ skill.name }}
                        </h4>
                        <h3 class="text-2xl font-bold text-white">{{ skill.width }}</h3>
                    </div>
                    <div class="mt-2 h-1 w-full bg-[#131d30] rounded-full">
                        <div class="h-1 rounded-full bg-primary" :style="`width: ${skill.width}`"></div>
                    </div>
                </div>
            </div>
            <div data-aos="flip-left">
                <h2 class="text-4xl font-bold text-white text-left mb-8 md:text-center md:mt-0 mt-8">My Experiences</h2>
                <div class="space-y-8 py-8" data-aos="fade-left">
                    <div v-for="element in experiences" :key="element.id"
                    class="flex items-center rounded-xl p-4 bg-[#111a3e] shadow-lg border border-[#1f1641]">
                        <div class="w-1/4">
                            <img src="https://img.icons8.com/ios-filled/100/ffffff/lawyer.png" alt="lawyer">
                        </div>
                        <div class="w-3/4 pl-4">
                            <h3 class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                                {{ element.role }}
                            </h3>
                            <p class="text-white">{{ element.company }}</p>
                            <p class="text-white">{{ element.date }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue';

const skills = ref([
    {
        id: 1,
        name: 'HTML & CSS',
        width: '85%'
    },
    {
        id: 2,
        name: 'Java',
        width: '70%'
    },
    {
        id: 3,
        name: 'JavaScript & Vue.js',
        width: '98%'
    },
    {
        id: 4,
        name: 'Spring Framework',
        width: '91%'
    },
    {
        id: 5,
        name: 'Design Patterns',
        width: '70%'
    },
    {
        id: 6,
        name: 'System Design',
        width: '80%'
    },
]);

const experiences = ref([
    {
        id: 1,
        role: 'Tech Lead',
        company: 'Tata Consultancy Services Limited',
        date: 'Feb 2023 - PRESENT'
    },
    {
        id: 2,
        role: 'Senior Software Developer',
        company: 'Fulcrum Worldwide Software Private Limited',
        date: 'Jan 2022 - Feb 2023'
    },
    {
        id: 3,
        role: 'Consultant',
        company: 'Virtusa Consulting Services',
        date: 'Nov 2018 - Dec 2021'
    },
    {
        id: 4,
        role: 'Associate Consultant Technology',
        company: 'Nityo Infotech',
        date: 'May 2018 - Nov 2018'
    },
    {
        id: 5,
        role: 'Software Engineer',
        company: 'Fervid Technology Solutions',
        date: 'Nov 2014 – May 2018'
    },
]);
</script>
