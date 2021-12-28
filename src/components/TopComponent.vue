<template>
  <div>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
      crossorigin="anonymous"
    />
    <nav
      class="navbar navbar-expand-lg navbar-light"
      style="background-color: #fff0e5"
    >
      <div class="container-fluid" style="background-color: #fff0e5">
        <img
          src="./codeAcademy.jpeg"
          alt="my-app\src\components\codeAcademy.jpeg"
        />
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarScroll"
          aria-controls="navbarScroll"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarScroll">
          <ul
            class="navbar-nav me-auto my-2 my-lg-0 navbar-nav-scroll"
            style="--bs-scroll-height: 100px"
          >
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="#"
                >Catalog</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Community</a>
            </li>
            <li class="nav-item dropdown">
              <a
                class="nav-link dropdown-toggle"
                href="#"
                id="navbarDropdown"
                role="button"
                data-bs-toggle="dropdown"
                aria-expanded="false"
              >
                resources
              </a>
              <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
                <li><a class="dropdown-item" href="#">Docs</a></li>
                <li><a class="dropdown-item" href="#">cheatsheet</a></li>
                <li><a class="dropdown-item" href="#">projects</a></li>
                <li><a class="dropdown-item" href="#">Articles</a></li>
                <li><a class="dropdown-item" href="#">Blogs</a></li>
              </ul>
            </li>
            <li class="nav-item">
              <a class="nav-link disabled">Pro-Pricing</a>
            </li>
          </ul>
          <form class="d-flex">
            <input
              class="form-control me-2"
              type="search"
              placeholder="Search"
              aria-label="Search"
            />
            <button class="btn btn-outline-success" type="submit">
              Search
            </button>
          </form>
        </div>
        <button v-on:click="say()" class="btn btn-outline-primary mx-lg-2">
          {{ btnText }}
        </button>
        <button class="btn btn-primary mx-lg-1">Sign Up</button>
      </div>
    </nav>
  </div>
</template>

<script>
import firebase from "firebase/compat/app";
import "firebase/compat/auth";

const firebaseConfig = {
  apiKey: "AIzaSyBSDpUN3-xjPAinfw5lIxqMC_4h9pcth9w",

  authDomain: "vue-project-38265.firebaseapp.com",

  projectId: "vue-project-38265",

  storageBucket: "vue-project-38265.appspot.com",

  messagingSenderId: "190212779702",

  appId: "1:190212779702:web:88122be4395cbfdbc68017",

  measurementId: "G-NS75V1NTRX",
};
export default {
  name: "TopComponent",
  data() {
    return {
      btnText: "login with google",
      disableBtn: false,
    };
  },
  methods: {
    say: function () {
      if (!firebase.apps.length) {
        firebase.initializeApp(firebaseConfig);
      }
      var provider = new firebase.auth.GoogleAuthProvider();

      firebase.auth().signInWithPopup(provider);
      this.btnText = "Logged in";
    },
  },
};
</script>
