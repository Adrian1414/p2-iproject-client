<script>

import { mapActions, mapState } from "pinia";
import { useMemberStore } from "../stores/member";

export default {
  name: "MemberProfile",
  computed: {
    ...mapState(useMemberStore, ["perMember"]),
  },
  methods: {
    ...mapActions(useMemberStore, ["memberProfile"]),
  },
  created() {
    this.memberProfile(this.$route.params.nickName);
  },
};
</script>

<template>
  <section class="relative block h-500-px">
    <div
      class="absolute top-0 w-full h-full bg-center bg-cover"
      style="
        background-image: url('https://upload.wikimedia.org/wikipedia/commons/a/ad/JKT48_Vector_Logo.png');
      "
    >
      <span
        id="blackOverlay"
        class="w-full h-full absolute opacity-50 bg-black"
      ></span>
    </div>
    <div
      class="top-auto bottom-0 left-0 right-0 w-full absolute pointer-events-none overflow-hidden h-70-px"
      style="transform: translateZ(0px)"
    >
      <svg
        class="absolute bottom-0 overflow-hidden"
        xmlns="http://www.w3.org/2000/svg"
        preserveAspectRatio="none"
        version="1.1"
        viewBox="0 0 2560 100"
        x="0"
        y="0"
      >
        <polygon
          class="text-blueGray-200 fill-current"
          points="2560 0 2560 100 0 100"
        ></polygon>
      </svg>
    </div>
  </section>
  <section class="relative py-16 bg-blueGray-200">
    <div class="container mx-auto px-4">
      <div
        class="relative flex flex-col min-w-0 break-words bg-white w-full mb-6 shadow-xl rounded-lg -mt-64"
      >
        <div class="px-6">
          <div class="flex flex-wrap justify-center">
            <div class="w-full lg:w-3/12 px-4 lg:order-2 flex justify-center">
              <div class="relative">
                <img
                  alt="..."
                  :src="perMember.imageUrl"
                  class="shadow-xl rounded-full h-auto align-middle border-none relative -m-16 -ml-20 lg:-ml-16  max-w-150-px"
                  style="aspect-ratio: 1/1; object-fit: cover;"
                />
              </div>
            </div>
            <div
              class="w-full lg:w-4/12 px-4 lg:order-3 lg:text-right lg:self-center"
            >
              <div class="py-6 px-3 mt-32 sm:mt-0">
                <RouterLink to="/members">
                  <button
                    class="bg-pink-500 active:bg-pink-600 uppercase text-white font-bold hover:shadow-md shadow text-xs px-4 py-2 rounded outline-none focus:outline-none sm:mr-2 mb-1 ease-linear transition-all duration-150"
                    type="button"
                  >
                    Back
                  </button>
                </RouterLink>
              </div>
            </div>
            <div class="w-full lg:w-4/12 px-4 lg:order-1">
              <div class="flex justify-center py-4 lg:pt-4 pt-8">
                <div class="mr-4 p-3 text-center">
                  <span
                    class="text-xl font-bold block uppercase tracking-wide text-blueGray-600"
                    >{{ perMember.totalShow }}</span
                  ><span class="text-sm text-blueGray-400">Total Show</span>
                </div>
                <div class="mr-4 p-3 text-center">
                  <span
                    class="text-xl font-bold block uppercase tracking-wide text-blueGray-600"
                    >{{ perMember.bloodType }}</span
                  ><span class="text-sm text-blueGray-400">Gol.Darah</span>
                </div>
                <div class="lg:mr-4 p-3 text-center">
                  <span
                    class="text-xl font-bold block uppercase tracking-wide text-blueGray-600"
                    >{{ perMember.height }}</span
                  ><span class="text-sm text-blueGray-400">Tinggi</span>
                </div>
              </div>
            </div>
          </div>
          <div class="text-center mt-14">
            <h3
              class="text-4xl font-semibold leading-normal text-blueGray-700 mb-2"
            >
              {{ perMember.nickName }}
            </h3>
            <div
              class="text-sm leading-normal mt-0 mb-2 text-pink-400 font-bold uppercase"
            >
              {{ perMember.fullName }}
            </div>
            <div class="mb-2 text-blueGray-600 mt-10">
              <i class="fab fa-instagram"></i>
              <a class="ml-2" href="">{{ perMember.instagram }}</a>
            </div>
            <div class="mb-2 text-blueGray-600">
              <i class="fab fa-twitter"></i>
              <a class="ml-1" href="">{{ perMember.twitter }}</a>
            </div>
          </div>
          <div class="mt-10 py-10 border-t border-blueGray-200 text-center">
            <div class="flex flex-wrap justify-center">
              <div class="w-full lg:w-9/12 px-4">
                <p class="mb-4 text-lg leading-relaxed text-blueGray-700">
                 Kalo mau Video call bayar bro, ada eventnya
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <footer class="relative bg-blueGray-200 pt-8 pb-6 mt-8">
      <div class="container mx-auto px-4">
        <div
          class="flex flex-wrap items-center md:justify-between justify-center"
        >
          <div class="w-full md:w-6/12 px-4 mx-auto text-center">
            <div class="text-sm text-blueGray-500 font-semibold py-1">
              Made By
              <a
                href="https://github.com/Adrian1414"
                class="text-blueGray-500 hover:text-gray-800"
                target="blank"
                >Adrian</a
              >
           
            </div>
          </div>
        </div>
      </div>
    </footer>
  </section>
</template>
