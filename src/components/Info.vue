<template>
  <div class="my-5" v-for="pf in profiles" :key="pf.id">
    <div class="grid sm:grid-cols-1 lg:grid-cols-2 ml-10 mr-10">
      <!-- <div class="ml-10 mr-0"> -->
      <!-- <h1 class="font-black mb-3">Protfolio</h1> -->
      <div class="my-5 h-28">
        <b>Profile</b>
        <img class="float-left mr-5 filter" :src="pf.img" width="100" />
        <div>
          <h1><b>Name : </b>{{ pf.first_name }} {{ pf.last_name }}</h1>
          <h1><b>Birthday : </b>{{ pf.birth_date }}</h1>
          <h1><b>Position : </b>{{ pf.position }}</h1>
        </div>
      </div>

      <div class="my-5">
        <b>CAREER OVERVIEW</b>
        <div class="pl-5">
          <p>{{ pf.overview }}</p>
        </div>
      </div>

      <div class="my-5">
        <b>EDUCATION</b>
        <div
          class="grid grid-cols-4 pl-5"
          v-for="ed in pf.educations"
          :key="ed.id"
        >
          <div>
            <b>{{ ed.s_year }} - {{ ed.e_year }}</b>
          </div>
          <div class="col-span-3">
            <ul>
              <li>
                <b>{{ ed.name }}, {{ ed.province }} {{ ed.postcode }}</b>
              </li>
              <li>
                <p>{{ ed.level }} (GPA {{ ed.GPA }})</p>
              </li>
            </ul>
          </div>
        </div>
      </div>

      <div class="my-5">
        <b>SKILL</b>
        <div class="grid grid-cols-2 pl-5">
          <div v-for="(value, name, index) in pf.skills">
            <b v-if="index === 0">Computer Languages</b>
            <b v-if="index === 1">Software & Tool</b>
            <ul class="pl-5" v-for="item in value">
              <li><b>> </b>{{ item }}</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="my-5">
        <b>CERTIFICAT</b>
        <div class="grid grid-cols-2 gap-10 pl-5">
          <div v-for="item in pf.certificats">
            <ul>
              <li>{{ item }}</li>
            </ul>
          </div>
        </div>
      </div>

      <!-- </div> -->
    </div>
  </div>
  <div class="grid justify-items-center">
    <router-link
      :to="{
        name: 'contact',
      }"
    >
      <button class="bg-black text-white font-bold py-2 px-4 rounded">
        View Contact
      </button>
    </router-link>
  </div>
</template>

<script>
export default {
  data: () => ({
    profiles: [
      {
        id: 1,
        first_name: 'Woramat',
        last_name: 'Khaowphong',
        img: 'https://reg.buu.ac.th/registrar/getstudentimage.asp?id=61160229',
        birth_date: '22/05/1999',
        position: 'Developer',
        overview:
          'I will bring my knowledge, abilities, and 4 years of university experience to make quality work. Have a good knowledge of programming languages and develop websites.',
        educations: [
          {
            id: 1,
            level:
              'B.Sc. (Information Tehnology) - in progress Faculty of Informatics',
            name: 'Burapha University',
            province: 'ChonBuri',
            postcode: '20130',
            s_year: 2018,
            e_year: 'Present',
            GPA: 3.23,
          },
          {
            id: 2,
            level: 'High School Certificat',
            name: 'Nawaminthrachinuthit Suankularbwittayalai Samutprakarn',
            province: 'Samutprakarn',
            postcode: '10280',
            s_year: 2012,
            e_year: 2017,
            GPA: 2.51,
          },
        ],
        skills: {
          com_lang: ['JavaScript', 'MySQL', 'HTML', 'Java', 'PHP', 'CSS'],
          software: [
            'XAMPP Control Panel',
            'Oracle VM VirtualBox',
            'MySQL Workbench',
            'Visual Studio Code',
            'Winscp',
            'Github',
            'Putty',
          ],
        },
        certificats: ['Milrotik MTCNA', 'Thai MOOC'],
      },
    ],
  }),
};
</script>
