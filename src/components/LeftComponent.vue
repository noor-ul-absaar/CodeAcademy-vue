<template>
  <div
    class="px-3 d-none d-lg-block"
    style="
      background-color: #fff0e5;
      width: 25%;
      height: 2843px;
      display: flexbox;
      padding-left: 20px;
      float: left;
    "
  >
    <a
      class="nav-link dropdown-toggle ml-5"
      href=""
      id="navbarDropdown"
      role="button"
      data-bs-toggle="dropdown"
      aria-expanded="false"
    >
      Languages
    </a>
    <ul class="" aria-labelledby="">
      <li v-for="d in languages" v-bind:key="d">
        <div class="abc" href="" style="padding-bottom: 20px">
          {{ d.title }}
        </div>
      </li>
    </ul>

    <a
      class="nav-link dropdown-toggle"
      href=""
      id="navbarDropdown"
      role="button"
      data-bs-toggle="dropdown"
      aria-expanded="false"
    >
      Subjects
    </a>
    <ul class="" aria-labelledby="dropdownMenuButton1">
      <li v-for="d in subjects" v-bind:key="d">
        <div class="abc" href="" style="padding-bottom: 20px">
          {{ d.title }}
        </div>
      </li>
    </ul>
    <div class="ad-container" style="border: 1px solid">
      <Adsense
        data-ad-client="ca-pub-1234567891234567"
        data-ad-slot="1234567890"
        data-ad-format="auto"
        :data-full-width-responsive="true"
      >
      </Adsense>
    </div>
  </div>
</template>

<script>
import left from "../left.json";
export default {
  data() {
    return {
      languages: left.languages,
      subjects: left.subjects,
    };
  },
  name: "LeftComponent",
};
</script>

<style>
.abc {
}
.abc:hover {
  color: blue;
}
</style>
