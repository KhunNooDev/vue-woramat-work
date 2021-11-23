<template>
  <div class="my-5" v-for="pf in profiles" :key="pf.id">
    <center><h1 class="font-black mb-3">Contact</h1></center>

    <div
      class="grid sm:grid-cols-2 lg:grid-cols-3 ml-10 mr-0 justify-items-center"
    >
      <div>
        <center>
          <img src="https://img.icons8.com/ios-filled/200/000000/address.png" />
          <p>{{ pf.address }}</p>
        </center>
      </div>
      <div>
        <center>
          <img src="https://img.icons8.com/ios/200/000000/mail.png" />
          <p>{{ pf.mail }}</p>
        </center>
      </div>
      <div>
        <center>
          <img
            src="https://img.icons8.com/ios-filled/200/000000/apple-phone.png"
          />
          <p>{{ pf.phone }}</p>
        </center>
      </div>
      <div>
        <center>
          <a :href="pf.github">
            <img
              src="https://img.icons8.com/ios-glyphs/200/000000/github.png"
            />
            <p>{{ pf.github }}</p>
          </a>
        </center>
      </div>
      <div>
        <center>
          <a :href="pf.facebook_url">
            <img
              src="https://img.icons8.com/ios-filled/200/000000/facebook--v1.png"
            />
            <p>{{ pf.facebook_url }}</p>
          </a>
        </center>
      </div>
      <div>
        <center>
          <a :href="pf.ig_url">
            <img
              src="https://img.icons8.com/ios-filled/200/000000/instagram-new--v1.png"
            />
            <p>{{ pf.ig_url }}</p>
          </a>
        </center>
      </div>
    </div>
  </div>
  <div class="grid justify-items-center">
    <router-link
      :to="{
        name: 'profile',
      }"
    >
      <button class="bg-black text-white font-bold py-2 px-4 rounded">
        View Profile
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
        address: '140/2, Moo 1, Bangpoo Samutprakarn, 10280',
        mail: '61160229@go.buu.ac.th',
        phone: '094-251-8136',
        github: 'https://github.com/KhunNooDev',
        facebook_url: 'https://www.facebook.com/DevKhunNoo',
        ig_url: 'https://www.instagram.com/khun.noo__/',
      },
    ],
  }),
};
</script>
