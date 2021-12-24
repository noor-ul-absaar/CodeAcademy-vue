<template>
  <div
    class="m-3 col-sm-12 col-md-6 col-lg-4"
    style="backgroundimage: row.url; width: 300px; height: 180px"
  >
    <div
      className=" mt-5 mx-4"
      type="button"
      style="
        backgroundcolor: white;
        textalign: center;
        height: 100px;
        width: 200px;
      "
    >
      <div style="textalign: start">{{ row.type }}</div>
      <b>
        <p>{{ row.title }}</p>
      </b>
      <p>{{ row.description }}</p>
      <div className="ms-5 mt-5" style="textalign: end">{{ row.end }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    row: JSON,
  },
  name: "PrintRow",
};
</script>
