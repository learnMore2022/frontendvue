<template>
    <section class="text-white mt-20" id="projects">
        <div class="px-4 xl:pl-16">
            <div class="mb-4 md:flex md:justify-between xl:pr-16">
                <h2 class="text-4xl font-bold text-white"> My Latest Projects</h2>
                <div class="flex space-x-4 mb-4 mt-5 md:mt-0">
                    <button class="hover:text-primary" v-for="category in ['all', 'web development', 'Mobile App']"
                        :key="category" @click="() => selectedCategory = category">
                        {{ category }}
                    </button>
                </div>
            </div>
            <ul class="px-4 sm:py-16 xl:pr-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3"
                data-aos="fade-right">
                <div v-for="project in filteredProjects" :key="project.id">
                    <div class="h-52 md:h-[24rem] rounded-t-xl relative group"
                    :style="{ backgroundImage: 'url(' + project.image + ')', backgroundSize: 'cover' }">                    
                    <div class="overlay items-center justify-center absolute top-0 left-0 w-full h-full bg-[#181818] bg-opacity-0
                    hidden group-hover:flex group-hover:bg-opacity-80 transition-all duration-500
                    ">
                        <a class="h-14 w-14 mr-2 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link"
                            :href="project.webURL"> <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true"
                                data-slot="icon"
                                class="h-10 w-10 text-[#ADB7BE] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2  cursor-pointer group-hover/link:text-white">
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M17.25 6.75 22.5 12l-5.25 5.25m-10.5 0L1.5 12l5.25-5.25m7.5-3-4.5 16.5">
                                </path>
                            </svg></a><a
                            class="h-14 w-14 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link"
                            :href="project.gitURL"> <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true"
                                data-slot="icon"
                                class="h-10 w-10 text-[#ADB7BE] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2  cursor-pointer group-hover/link:text-white">
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M2.036 12.322a1.012 1.012 0 0 1 0-.639C3.423 7.51 7.36 4.5 12 4.5c4.638 0 8.573 3.007 9.963 7.178.07.207.07.431 0 .639C20.577 16.49 16.64 19.5 12 19.5c-4.638 0-8.573-3.007-9.963-7.178Z">
                                </path>
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"></path>
                            </svg></a>
                    </div>
                </div>
                <div class="text-white rounded-b-xl mt-3 bg-[#111a3e] shadow-lg border border-[#1f1641] py-6 px-4">
                    <h3 class="text-lg font-semibold uppercase lg:text-xl"> {{ project.title }}</h3>
                    <p class="text-[#ADB7BE]">{{ project.description }}</p>
                    <div class="flex flex-wrap p-2.5">
                        <div v-for="technology in project.technologies" :key="technology" class="text-center ml-1 mt-1 rounded-3xl bg-[#111827]"
                        style="box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1); border: 1px solid #111827;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);"
                        >
                    <p class="px-1 py-2">{{ technology }}</p>
                    </div>
                    </div>
                </div>
                </div>
            </ul>
        </div>
    </section>
</template>
<script setup>
import { ref, computed } from 'vue';

const Projects = ref([
    {
        id: 1,
        category: 'web development',
        image: 'src/assets/project.png',
        title: 'project 1',
        description: 'This is the core sales tools used for creating the quote. SalgsNøkkelen is a web-based application used by the Sales team of Tryg. The insurance sellers login to this application through KundeNøkkelen and can create /view/ update/ reject offers, created for customers before offering it to them. Apart from sellers in Tryg, SalgsNøkkelen is also used by insurance sellers from Nordea bank, Enter - a car insurance company, both of whom have tie-ups with Tryg for providing insurance to their customers and ‘Franchise ’s in Norway.Insurance sellers from Tryg and Enter/ Nordea bank login to SalgsNøkklen from KundeNøkkelen Sellers from Nordea bank , can also login via other interfaces but are redirected to the SN’s login page.!',
        technologies: ['struts', 'java', 'spring', 'Hibernate', 'Rest', 'Soap', 'RMI', 'java script', 'Maven', 'Agile'],
        gitURL: '',
        webURL: ''
    },
    {
        id: 2,
        category: 'Mobile App',
        image: 'src/assets/mobile.jpg',
        title: 'project 1',
          description: `This is the core jar or platform of master card which is consumed by all the other Api of master card.
                        • We build a common functionality which will be used by all the Api.
                        • Anything new approach or Research on implementation of new functionality is handled by this team for master card!`,
        technologies: ['J2EE', 'Spring', 'Hibernate', 'Rest', 'Soap', 'Apache camel', 'Maven', 'Agile'],
        gitURL: '',
        webURL: ''
    },
    {
        id: 3,
        category: 'web development',
        image: 'src/assets/project.png',
        title: 'project 1',
        description: 'SPEED(Solution pricing and end to end design)- It is a part of GS portal .This tool is use to provide end to end design creation as per customer requirement in UK, from customer creation to quote creation, pricing and end up in generating reports and BOM(Billing of Material )which is fed to the lower system. For fulfilment of order. Troubleshoot complex Enterprise networks.',
        technologies: ['vue.js 3', 'J2EE', 'Spring', 'Hibernate', 'Rest', 'Soap', 'Apache camel', 'Maven', 'Agile'],
        gitURL: '',
        webURL: ''
    },
    {
        id: 4,
        category: 'Mobile App',
        image: 'src/assets/mobile.jpg',
        title: 'project 1',
        description: 'RSQE(Refactor Sales Quote Engine) this is a sales quoting engine which quote a price of the component by interacting with various different api based on the user selected requirement.',
        technologies: ['vue.js 3', 'J2EE', 'Spring', 'Hibernate', 'Rest', 'Soap', 'Apache camel', 'Maven', 'Agile'],
        gitURL: '',
        webURL: ''
    },
    {
        id: 5,
        category: 'web development',
        image: 'src/assets/project.png',
        title: 'project 1',
        description: 'RDE(Risk Decision Engine) this has two journey one in fraud and other is credit based on the input fetched from different service we decide the whether the customer is eligible for card or not.!',
        technologies: ['vue.js 3', 'J2EE', 'Spring', 'Hibernate', 'Rest', 'Soap', 'Apache camel', 'Maven', 'Agile','LUCY(Rule Engine)'],
        gitURL: '',
        webURL: ''
    },
  
]);

const selectedCategory = ref('all');
const filteredProjects = computed(() => {
    if (selectedCategory.value === 'all') {
        return Projects.value;
    }
    return Projects.value.filter(project => project.category.toLocaleLowerCase() === selectedCategory.value.toLocaleLowerCase());
})

</script>
