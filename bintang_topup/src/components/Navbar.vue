<script>
import { mapState, mapActions  } from 'pinia';
import { useCounterStore } from '../stores/counter'

export default {
  
  data() {
    return {
     
    };
  },
  computed:{
    ...mapState(useCounterStore, ["access_token"])
  },
  methods:{
    ...mapActions(useCounterStore,["logout"])
  }
};

</script>
<template>
    <section id="nav">
        <div
          class="z-[1000] bg-white fixed shadow-xl py-2 top-0 left-0 right-0 flex justify-between items-center"
        >
          <div class="logo">
            <a href="#"
              ><img
                src="https://ik.imagekit.io/bintangtopup/bintangtopup/card/logo.png?ik-sdk-version=javascript-1.4.3&updatedAt=1673486183282"
                width="125px"
            /></a>
          </div>
          <div class="flex justify-between">
            <ul id="MenuItems">
              <router-link to="/"
                class="p-2 mx-2 rounded-full hover:text-white hover:bg-green-400"
                href="#"
                >Home</router-link
              >
              <router-link to="/product"
                class="p-2 mx-2 rounded-full hover:text-white hover:bg-green-400"
                >Produk</router-link
              >
              <a
                class="p-2 mx-2 rounded-full hover:text-white hover:bg-green-400"
                href="https://www.instagram.com/bintang_topup/"
                >Tentang</a
              >
              <a
                class="p-2 mx-2 rounded-full hover:text-white hover:bg-green-400"
                href="https://api.whatsapp.com/send?phone=6285718707307"
                >Bantuan</a
              >
              <router-link  to="/login" v-if='!access_token'
                class="p-2 mx-2 rounded-full hover:text-white hover:bg-green-400"
                >Masuk</router-link
              >
              <a v-if='!access_token'
                class="p-2 mx-2 rounded-full hover:text-white hover:bg-green-400"
                href="/register"
                >Daftar</a
              >
              <a @click.prevent="logout" v-if='access_token'
                class="p-2 mx-2 rounded-full hover:text-white hover:bg-green-400"
                href="#"
                >Keluar</a
              >
            </ul>
          </div>
        </div>
      </section>
</template>