<template>
  <div style="background-color: #fff0e5">
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
      crossorigin="anonymous"
    />
    <div class="grid-container">
      <header class="header">
        <TopComponent />
      </header>
      <main class="main">
        <LeftComponent />
        <RightComponent />
      </main>
      <footer class="footer">
        <BottomComponent />
      </footer>
    </div>
    <GoogleMap />
    <share_it />
  </div>
</template>
<script>
import TopComponent from "./components/TopComponent.vue";
import LeftComponent from "./components/LeftComponent.vue";
import RightComponent from "./components/RightComponent.vue";
import GoogleMap from "./components/GoogleMap.vue";
import share_it from "./components/share-it.vue";
import BottomComponent from "./components/BottomComponent.vue";
import { initializeApp } from "firebase/app";
import firebase from "firebase/app";
document.body.style="background:#fff0e5";

const firebaseConfig = {
  apiKey: "AIzaSyBSDpUN3-xjPAinfw5lIxqMC_4h9pcth9w",
  authDomain: "vue-project-38265.firebaseapp.com",
  projectId: "vue-project-38265",
  storageBucket: "vue-project-38265.appspot.com",
  messagingSenderId: "190212779702",
  appId: "1:190212779702:web:88122be4395cbfdbc68017",
  measurementId: "G-NS75V1NTRX",
};
const app = initializeApp(firebaseConfig);
console.log(app);

export default {
  name: "App",
  components: {
    TopComponent,
    LeftComponent,
    RightComponent,
    BottomComponent,
    GoogleMap,
    share_it,
  },
  methods: {
    say: function () {
      var provider = new firebase.auth.GoogleAuthProvider();
      firebase.auth().signInWithPopup(provider);
    },
  },
};
</script>

<style>
.grid-container {
  display: grid;
  grid-template-areas: "header" "main" "footer";
  height: 100%;
}
a {
  text-decoration: none;
  color: black;
}
a:hover {
  color: blue;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
