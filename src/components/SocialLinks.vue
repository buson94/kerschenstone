<template>
  <div id="socials_col" v-for="social in socials" :key="social.id">
    <!-- Brauchen 100 Subs auf YouTube um eine Custom-URL erstellen zu können, dann kann man sich auch diesen Teil sparen -->
    <a v-if="social.name == 'Youtube'" href="https://www.youtube.com/channel/UCFv7qxKxMObgNyvFpEq_sTg" target="_blank">
      <img id="social_img" :alt="social.name + ' logo'" src="../assets/Youtube.svg">
    </a>
    <a v-else :href="`https://${social.name}.com/${bandName}`" target="_blank">
      <img id="social_img" :alt="social.name + ' logo'" :src="require(`../assets/${social.name}.svg`)">
    </a>
  </div>
</template>

<script>
export default {
  name: "SocialLinks",
  props: {
    bandName: {
      required: true,
      type: String,
    }
  },
  data: () => ({
    socials: [
      { id: 1, name: "Twitter" },
      { id: 2, name: "Instagram" },
      { id: 3, name: "Soundcloud" },
      { id: 4, name: "Youtube" },
      { id: 5, name: "Facebook" }
    ]
  })
}
</script>

<style>
#socials_col {
  max-width: 120px;
  min-width: 50px;
  text-align: center;
  font-size: 1.4em;
  margin: 8px 0 8px 0;
}

#social_img {
  min-width: 80px;
  margin: auto 10px;
}
</style>