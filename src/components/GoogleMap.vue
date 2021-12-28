<template>
  <div>
    <div>
      <h2>Share more on Social Media</h2>
    </div>
    <br />
    <share-it
      :icons="true"
      :targets="['twitter', 'facebook', 'reddit', 'email']"
    />
  </div>
</template>

<script>
export default {
  name: "share_it",
};
</script>
