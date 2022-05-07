<template>
  <div class="home">
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
                <router-link class="nav-link active" to="/">Home</router-link>
              </li>
              <li class="nav-item">
                <router-link class="nav-link" to="/api">Baca</router-link>
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
      <!-- Gallery -->
      <section id="my-gallery">
        <div class="row">
          <div class="col">
            <div class="d-flex h-100">
              <div class="justify-content-center align-self-center">
                <h2><strong>Sudakah anda membaca al-qur'an</strong> <br />Hari ini</h2>
                <router-link class="btn btn-lg btn-success" to="/api">Mari membaca</router-link>
              </div>
            </div>
          </div>

          <div class="col">
            <img src="../assets/baca.jpg" alt="" width="70%" />
          </div>
        </div>
      </section>

      <!-- Akhir Gallery -->
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
        <path
          fill="#ffc107"
          fill-opacity="1"
          d="M0,64L24,64C48,64,96,64,144,74.7C192,85,240,107,288,144C336,181,384,235,432,234.7C480,235,528,181,576,181.3C624,181,672,235,720,218.7C768,203,816,117,864,106.7C912,96,960,160,1008,186.7C1056,213,1104,203,1152,192C1200,181,1248,171,1296,165.3C1344,160,1392,160,1416,160L1440,160L1440,320L1416,320C1392,320,1344,320,1296,320C1248,320,1200,320,1152,320C1104,320,1056,320,1008,320C960,320,912,320,864,320C816,320,768,320,720,320C672,320,624,320,576,320C528,320,480,320,432,320C384,320,336,320,288,320C240,320,192,320,144,320C96,320,48,320,24,320L0,320Z"
        ></path>
      </svg>
      <!-- Footer -->
      <footer id="c" class="bg-warning text-center p-3">
        <p>Copyright <a href="https://www.instagram.com/bintang_fauzan14/">Bintang Fauzan Dyan</a></p>
      </footer>
      <!-- Akhir footer -->
    </body>
  </div>
</template>

<style>
#p {
  font-family: "Oswald", sans-serif;
}
</style>
