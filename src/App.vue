<template>
  <div id="main">
    <img id="header_img" alt="Kerschenstone logo" src="./assets/logo.svg">
    <h1>Willkommen bei {{name}}!</h1>
    Eine vor {{new Date().getFullYear()-founded}} Jahren gegründete Pop/Rock-Band aus {{hometown}}!
    <h2>Social Media Profile</h2>
    <div id="socials_row">
      <div id="socials_col" v-for="social in socials" :key="social.id">
        <!-- Brauchen 100 Subs auf YouTube um eine Custom-URL erstellen zu können, dann kann man sich auch diesen Teil sparen -->
        <a v-if="social.name == 'Youtube'" href="https://www.youtube.com/channel/UCFv7qxKxMObgNyvFpEq_sTg" target="_blank">
          <img id="social_img" v-bind:alt="social.name + ' logo'" src="./assets/Youtube.svg">
        </a>
        <a v-else v-bind:href="'https://' + social.name + '.com/' + name" target="_blank">
          <img id="social_img" v-bind:alt="social.name + ' logo'" :src="require('./assets/' + social.name + '.svg')">
        </a>
      </div>
    </div>
    <h2>Direkter Kontakt</h2>
    <address>
      <a href="mailto:rock.this@kerschenstone.de" target="_blank">
        rock.this@kerschenstone.de
      </a>
    </address>
  </div>
</template>

<script>
export default {
  name: 'App',
  data: () =>({
    name: 'Kerschenstone',
    founded: 2011,
    hometown: 'Delmenhorst',
    socials: [
      {id: 1, name: "Twitter"},
      {id: 2, name: "Instagram"},
      {id: 3, name: "Soundcloud"},
      {id: 4, name: "Youtube"},
      {id: 5, name: "Facebook"}
    ]
  })
}
</script>

<style>
body{
  margin: 0;
  background: #3a81c3 linear-gradient(to bottom, #1e5799 0%, #3a81c3 48%, #3a81c3 100%) no-repeat;
  font-family: "Roboto", "Arial", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
}
a{
  color: #ffffff;
  font-family: "Roboto", "Arial", sans-serif;
  text-decoration: none;
  font-style: normal;
}
#main {
  min-width: 50%;
  max-width: 80%;
  margin: 50px auto 0 auto;
}
#header_img{
  min-height: 50px;
  max-height: 150px;
}
#socials_row{
  align-items: center;
  justify-content: center;
  margin: 0;
  padding: 0;
  display: flex;
  flex: 1;
}
#socials_col{
  text-align: center;
  font-size: 1.4em;
  margin: 8px 0 8px 0;
}
#social_img{
  width: 120px;
  margin: auto 10px;
}
</style>
