<template>
  <div id="list-group">
    <head>
      <link rel="preconnect" href="https://fonts.googleapis.com" />
      <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
      <link href="https://fonts.googleapis.com/css2?family=Oswald:wght@300&display=swap" rel="stylesheet" />
    </head>
    <body id="p">
      <!-- NavBar -->
      <nav class="navbar navbar-expand-lg navbar-light bg-warning shadow fixed-top">
        <div class="container">
          <a class="navbar-brand" href="#">Mari membaca Al-Qur'an</a>
          <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav ms-auto">
              <li class="nav-item">
                <router-link class="nav-link" to="/">Home</router-link>
              </li>
              <li class="nav-item">
                <router-link class="nav-link active" to="/api">Baca</router-link>
              </li>
              <li class="nav-item">
                <router-link class="nav-link" to="/about">About me</router-link>
              </li>
              <li class="nav-item">
                <router-link class="nav-link" to="/contact">Contact</router-link>
              </li>
            </ul>
          </div>
        </div>
      </nav>
      <!-- Akhir NavBar -->
    </body>
    <!-- surah -->
    <section class="search">
      <input type="number" v-model="inputnomor" class="input form-control" placeholder="Nomor Surah" />
      <button @click="cari" class="btn btn-lg btn-success">Cari</button>
    </section>

    <section class="surah">
      <div class="judull">
        <h1 v-if="namaSurah" class="judul">{{ namaSurah.name_simple }}</h1>
      </div>

      <div class="audio">
        <p v-if="audio">
          <audio controls class="audioa">
            <source :src="audio.audio_url" type="audio/mpeg" />
            Your browser does not support the audio element.
          </audio>
        </p>
      </div>
    </section>

    <section class="hasil">
      <div class="hasill">
        <ul class="lista">
          <li class="list-group-item ayat d-flex justify-content-end" v-for="ayat in ayah" :key="ayat.id">{{ ayat.text_uthmani }} {{ ayat.text }}</li>
        </ul>
      </div>
    </section>
    <!-- Akhir Surah -->
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      ayah: [],
      audio: null,
      namaSurah: null,
      inputnomor: "",
    };
  },

  methods: {
    async cari() {
      let nomor = this.inputnomor;
      let ayat = `https://api.quran.com/api/v4/quran/verses/uthmani?chapter_number=${nomor}`;
      let terjemahan = "https://api.quran.com/api/v4/quran/translations/134?chapter_number=" + nomor;

      let judul = "https://api.quran.com/api/v4/chapters?language=en";
      let audio = "https://api.quran.com/api/v4/chapter_recitations/2?language=en";

      if (nomor <= 0 || nomor > 114) {
        alert("masukkan nomor dengan benar");
      } else {
        const reqAyat = axios.get(ayat);
        const reqterjemahan = axios.get(terjemahan);
        const reqJudul = axios.get(judul);
        const reqaudio = axios.get(audio);

        axios.all([reqAyat, reqterjemahan, reqJudul, reqaudio]).then(
          axios.spread((...response) => {
            const responseAyat = response[0];
            const responseterjemahan = response[1];
            const responseJudul = response[2];
            const responseaudio = response[3];

            const a = responseAyat.data.verses;
            const b = responseterjemahan.data.translations;

            const gabung = (a, b) => {
              const res = [];

              for (let i = 0; i < a.length + b.length; i++) {
                if (i % 2 === 0) {
                  res.push(a[i / 2]);
                } else {
                  res.push(b[(i - 1) / 2]);
                }
              }
              return res;
            };

            this.ayah = gabung(a, b);
            this.audio = responseaudio.data.audio_files[nomor - 1];
            this.namaSurah = responseJudul.data.chapters[nomor - 1];
          })
        );
      }
    },
  },
};
</script>

<style>
#p {
  font-family: "Oswald", sans-serif;
}
</style>
