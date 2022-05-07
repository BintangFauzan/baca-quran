<template>
  <div id="contact">
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
                <router-link class="nav-link" to="/api">Baca</router-link>
              </li>
              <li class="nav-item">
                <router-link class="nav-link" to="/about">About me</router-link>
              </li>
              <li class="nav-item">
                <router-link class="nav-link active" to="/contact">Contact</router-link>
              </li>
            </ul>
          </div>
        </div>
      </nav>
      <!-- Akhir NavBar -->
      <!-- contact -->
      <div class="container">
        <div class="row text-center">
          <div class="col mt-5">
            <h2>Contact</h2>
          </div>
        </div>
        <div class="row justify-content-center">
          <div class="col-md-6">
            <form>
              <div class="mb-3">
                <label for="name" class="form-label">Nama Lengkap</label>
                <input type="text" class="form-control" id="name" aria-describedby="name" />
              </div>
              <div class="mb-3">
                <label for="email" class="form-label">Email</label>
                <input type="email" class="form-control" id="email" aria-describedby="email" />
              </div>
              <div class="mb-3">
                <label for="nomor-hp" class="form-label">Nomor telepon</label>
                <input type="number" class="form-control" id="nomor-hp" aria-describedby="nomor-hp" />
              </div>
              <div class="mb-3">
                <label for="pesan" class="form-label">Pesan</label>
                <textarea class="form-control" id="pesan" rows="3"></textarea>
              </div>
              <button type="submit" class="btn btn-primary">Kirim</button>
            </form>
          </div>
        </div>
      </div>
      <!-- Akhir contact -->
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

<script>
export default {};
</script>

<style>
#p {
  font-family: "Oswald", sans-serif;
}
</style>
