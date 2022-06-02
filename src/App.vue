<template>
  <div id="main">
    <img id="header_img" alt="Kerschenstone logo" src="./assets/logo.svg">
    <h1>Willkommen bei {{name}}!</h1>
    Eine vor {{new Date().getFullYear()-founded}} Jahren gegründete Pop/Rock-Band aus {{hometown}}!
    <h2>Social Media Profile</h2>
    <div id="socials_row">
      <SocialLinks :bandName="name" />
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
import SocialLinks from "./components/SocialLinks.vue"
export default {
    name: "App",
    data: () => ({
        name: "Kerschenstone",
        founded: 2011,
        hometown: "Delmenhorst",
        components: {
            SocialLinks
        }
    }),
    components: { SocialLinks }
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
</style>
