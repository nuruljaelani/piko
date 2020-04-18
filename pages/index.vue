/* eslint-disable no-console */
<template>
  <div>
    <header class="w-full bg-white shadow-lg mb-8 lg:mb-10">
      <Navbar />
    </header>
    <div class="flex flex-col lg:flex-row container mx-auto px-4 md:px-10">
      <div class="w-full lg:w-1/2 max-w-3xl bg-gray-400 rounded mr-0 md:mr-4 shadow-md overflow-hidden" style="height:50vh">
        <VueSlickCarousel v-bind="settings">
          <div>
            <img src="~/assets/coronavirus-news-on-screen-3970332.jpg" alt="" class="w-full object-fill">
          </div>
          <div>
            <img src="~/assets/coveid19-text-on-paper-3952238.jpg" alt="" class="w-full object-fill">
          </div>
          <div>
            <img src="~/assets/person-washing-his-hand-545014.jpg" alt="" class="w-full object-fill">
          </div>
          <div>
            <img src="~/assets/woman-holding-sign-3951602.jpg" alt="" class="w-full object-fill">
          </div>
        </VueSlickCarousel>
        <!-- <div>
          <img src="~/assets/coronavirus-news-on-screen-3970332.jpg" alt="" class="w-full object-fill">
        </div> -->
      </div>
      <div class="flex lg:flex-col lg:w-1/2 mt-4 lg:mt-0 items-end justify-between">
        <div class="bg-white rounded w-full max-w-xl mr-4 lg:mr-0 shadow-md text-center pt-10 font-semibold" style="height:9rem">
          <p class="text-lg">
            Call Center
          </p>
          <p class="text-green-600 mt-2 text-2xl">
            119
          </p>
        </div>
        <div class="bg-white rounded w-full max-w-xl shadow-lg pt-10 font-semibold text-center" style="height:9rem">
          <p class="text-lg">
            Dinkes Jabar
          </p>
          <p class="mt-2 text-green-600 text-2xl">
            0811 2093 306
          </p>
        </div>
      </div>
    </div>
    <div class="flex flex-col container mx-auto my-10 px-4 md:px-10">
      <div class="text-lg md:text-2xl font-semibold border-gray-600 border-b-2">
        Data Terbaru Covid 19
      </div>
      <div class="flex flex-col md:flex-row justify-between">
        <div class="uppercase bg-red-100 rounded p-4 border border-gray-400 my-4 max-w-sm w-full md:w-1/3">
          <p class="font-semibold">
            Positif Covid 19
          </p>
          <hr>
          <p class="mt-4 font-semibold text-xl">
            Indonesia   : {{ positif }}
          </p>
        </div>
        <div class="uppercase bg-green-300 rounded p-4 border border-gray-400 my-4 max-w-sm w-full md:w-1/3">
          <p class="font-semibold">
            Sembuh
          </p>
          <hr>
          <p class="mt-4 font-semibold text-xl">
            Indonesia   : {{ sembuh }}
          </p>
        </div>
        <div class="uppercase bg-red-300 rounded p-4 border border-gray-400 my-4 max-w-sm w-full md:w-1/3">
          <p class="font-semibold">
            Meningggal
          </p>
          <hr>
          <p class="mt-4 font-semibold text-xl">
            Indonesia   : {{ meninggal }}
          </p>
        </div>
      </div>
      <div class="inline-block mt-6 bg-white rounded-md shadow-md p-4">
        <p class="font-semibold border-b-2 py-2">
          Data berdasarkan Provinsi
        </p>
        <div class="min-w-full overflow-y-auto" style="height:70vh">
          <table class="w-full border-gray-300 border my-4">
            <thead class="border-b-2 border-gray-300">
              <tr>
                <th class="py-2 px-4 text-left">
                  No
                </th>
                <th class="py-2 px-4 text-left">
                  Provinsi
                </th>
                <th class="py-2 px-4 text-left">
                  Positif
                </th>
                <th class="py-2 px-4 text-left">
                  Sembuh
                </th>
                <th class="py-2 px-4 text-left">
                  Meninggal
                </th>
              </tr>
            </thead>
            <tbody v-for="(item, index) in provinsi" :key="index">
              <tr>
                <td class="px-4 py-2">
                  {{ index+1 }}
                </td>
                <td class="px-4 py-2">
                  {{ item.attributes.Provinsi }}
                </td>
                <td class="px-4 py-2">
                  {{ item.attributes.Kasus_Posi }}
                </td>
                <td class="px-4 py-2">
                  {{ item.attributes.Kasus_Semb }}
                </td>
                <td class="px-4 py-2">
                  {{ item.attributes.Kasus_Meni }}
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>

      <!-- Data global -->
      <div class="inline-block mt-6 bg-white rounded-md shadow-md p-4 mt-8">
        <p class="font-semibold border-b-2 py-2">
          Data Covid19 Global ( Data by John Hopkins University )
        </p>
        <div class="min-w-full overflow-y-auto" style="height:70vh">
          <table class="w-full border-gray-300 border my-4">
            <thead class="border-b-2 border-gray-300">
              <tr>
                <th class="py-2 px-4 text-left">
                  No
                </th>
                <th class="py-2 px-4 text-left">
                  Negara
                </th>
                <th class="py-2 px-4 text-left">
                  Positif
                </th>
                <th class="py-2 px-4 text-left">
                  Sembuh
                </th>
                <th class="py-2 px-4 text-left">
                  Meninggal
                </th>
              </tr>
            </thead>
            <tbody v-for="(item, index) in global" :key="index">
              <tr>
                <td class="px-4 py-2">
                  {{ index+1 }}
                </td>
                <td class="px-4 py-2">
                  {{ item.attributes.Country_Region }}
                </td>
                <td class="px-4 py-2">
                  {{ item.attributes.Confirmed }}
                </td>
                <td class="px-4 py-2">
                  {{ item.attributes.Recovered }}
                </td>
                <td class="px-4 py-2">
                  {{ item.attributes.Deaths }}
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
    <footer class="mt-10">
      <div class="bg-gray-900 h-20">
        <div class="text-white text-center pt-8">
          Create by Jay Weinberg | 2020
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
import Navbar from '../components/Navbar'
export default {
  components: {
    Navbar,
    VueSlickCarousel
  },
  async asyncData ({ $axios }) {
    const covid = await $axios.$get('https://api.kawalcorona.com/indonesia')
    const prov = await $axios.get('https://api.kawalcorona.com/indonesia/provinsi')
    const glob = await $axios.get('https://api.kawalcorona.com/')
    // eslint-disable-next-line no-console
    return {
      positif: covid[0].positif,
      sembuh: covid[0].sembuh,
      meninggal: covid[0].meninggal,
      provinsi: prov.data,
      global: glob.data
    }
  },
  data () {
    return {
      settings: {
        dots: true,
        dotsClass: 'slick-dots custom-dot-class',
        edgeFriction: 0.35,
        infinite: true,
        speed: 700,
        slidesToShow: 1,
        slidesToScroll: 1,
        autoplay: true,
        autoplaySpeed: 2000
      }
    }
  }
}
</script>
