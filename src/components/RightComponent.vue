<template>
  <div style="backgroundcolor: #fff0e5">
    <div
      style="
        display: flexbox;
        float: right;
        width: 75%;
        background-color: #fff0e5;
        paddingleft: 2%;
      "
    >
      <div
        style="position: absolute; z-index: 1; margin-left: 20%; margin-top: 1%"
      >
        <button class="btn btn-link">
          <strong>Not sure where to begin ? Take our Quiz ?</strong>
        </button>
      </div>
      <div
        className="col-sm-12 col-md-6 col-lg-4"
        style="margin-left: 10%; position: relative; z-index: 0"
      >
        <img style="width: 700px" src="../I1.jpeg" alt="../I1.jpeg" />
      </div>

      <h3>Most Popular</h3>
      <div class="row">
        <div v-for="l in languages" v-bind:key="l" class="col">
          <div
            class="lang m-3 col col-sm-12 col-md-6 col-lg-4"
            v-bind:style="{
              backgroundImage: 'url(' + l.url + ')',
              width: '300px',
              height: '180px',
              padding: '40px',
            }"
          >
            <div
              className=" mt-5 mx-4"
              type="button"
              style="
                background-color: white;
                text-align: center;
                align-items: center;
                height: 100px;
                width: 200px;
              "
            >
              <div style="textalign: center">{{ l.type }}</div>
              <b>
                <p>{{ l.title }}</p>
              </b>
              <p>{{ l.description }}</p>
              <div className="ms-5 mt-5" style="textalign: end">
                {{ l.end }}
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="row">
        <div v-for="l in languages" v-bind:key="l" class="col">
          <div
            class="lang m-3 col col-sm-12 col-md-6 col-lg-4"
            v-bind:style="{
              backgroundImage: 'url(' + l.url + ')',
              width: '300px',
              height: '180px',
              textalign: 'centre',
              padding: '40px',
            }"
          >
            <div
              className=" mt-5 mx-4"
              type="button"
              style="
                background-color: white;
                text-align: center;
                align-items: center;
                height: 100px;
                width: 200px;
              "
            >
              <div style="textalign: start">{{ l.type }}</div>
              <b>
                <p>{{ l.title }}</p>
              </b>
              <p>{{ l.description }}</p>
              <div className="ms-5 mt-5" style="textalign: end">
                {{ l.end }}
              </div>
            </div>
          </div>
        </div>
      </div>

      <h3>Get Inspired</h3>

      <div class="row">
        <div class="col-5">
          <div class="row">
            <div v-for="c in cards" v-bind:key="c" class="col">
              <div className="col-sm-12 col-md-6 col-lg-4" style="width: 300px">
                <span>{{ c.span }}</span>
                <h3>{{ c.h3 }}</h3>
              </div>
            </div>
          </div>
        </div>

        <div class="col-7">
          <img
            style="width: 500px; height: 400px"
            src="https://images.ctfassets.net/go6kr6r0ykrq/12jJ3cWg6gTfZFfGZZZxM8/ff0e4bd1d60c86f8580a067e2f267854/image__7_.png"
            alt="https://static-assets.codecademy.com/assets/components/resources/blog/standard/group-59.svg"
          />
        </div>
      </div>

      <div class="row">
        <div v-for="c in cards" v-bind:key="c" class="col">
          <div
            className="col-sm-12 col-md-6 col-lg-4"
            style="width: 300px; height: 180px"
          >
            <div
              v-bind:style="{
                backgroundImage: 'url(' + c.image + ')',
                width: '300px',
                height: '180px',
              }"
            ></div>
            <span>{{ c.span }}</span>
            <h3>{{ c.h3 }}</h3>
          </div>
        </div>
      </div>
      <br />
      <br />
      <br />
      <br />
      <br />
      <br />

      <div class="row">
        <div class="col-6">
          <img
            style="object-fit: cover; display: block; height: 180px"
            src="https://static-assets.codecademy.com/assets/components/resources/article/standard/group-7.svg"
            alt="https://static-assets.codecademy.com/assets/components/resources/article/standard/group-7.svg"
          />
          <span>Article</span>
          <h3>Consider Design While You Build</h3>
        </div>

        <div class="col-6">
          <div class="row">
            <div v-for="c in Big_Card_Side" v-bind:key="c" class="col">
              <div className="col-sm-12 col-md-6 col-lg-4" style="width: 300px">
                <span>{{ c.span }}</span>
                <h3>{{ c.h3 }}</h3>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="row">
        <div v-for="c in cards" v-bind:key="c" class="col">
          <div
            v-if="c.span == 'Video'"
            className="col-sm-12 col-md-6 col-lg-4"
            style="width: 300px; height: 180px"
          >
            <div
              v-bind:style="{
                backgroundImage: 'url(' + c.image + ')',
                width: '300px',
                height: '180px',
              }"
            ></div>
            <span>{{ c.span }}</span>
            <h3>{{ c.h3 }}</h3>
          </div>
        </div>
      </div>

      <br />
      <br />
      <br />
      <br />
      <br />
      <br />
    </div>
  </div>
</template>

<script>
import right from "../right.json";
//import img from "../I1.jpeg";
export default {
  name: "RightComponent",
  props: {
    row: JSON,
  },
  data() {
    return {
      languages: right.languages,
      cards: right.cards,
      Big_Card_Side: right.Big_Card_Side,
      get_inspired: right.get_inspired,
      get_inspired_image: right.get_inspired_image,
    };
  },
};
</script>

<style>
.lang {
}

.lang:hover {
  box-shadow: 10px 10px;
}
</style>
