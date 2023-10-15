<template>
  <v-container grid-list-xl>
    <h2>
      <span>Web</span>
      <span class="green--text">Portfolio</span>
    </h2>
    <v-layout row justify-center align-center wrap class="d-flex mt-4 pt-2">

      <v-flex xs12 sm6 md4 lg4 xl4 v-for="project in projects">
        <a v-bind:href="project.demo" target="_blank" class="text-decoration-none text-center">
          <v-card hover flat color="transparent" class="px-2">
            <v-img :src="project.poster" :alt="project.title" height="230" contain
              lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif"></v-img>
            <v-card-title primary-title class="justify-center">{{ project.title }}</v-card-title>
            <v-chip color="green" text-color="white" v-for="tech in project.tech">{{ tech }}</v-chip>
          </v-card>
        </a>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  metaInfo: {
    title: "Web Portfolio",
    titleTemplate: "%s ← Peter's Space",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        name: "description",
        content:
          "Peter Samir's Web Portfolio Vue Vue.js Nuxt Nuxt.js HTML CSS Vuetify Axios GraphQL JavaScript Web Developer Front-End Frontend Designer App Responsive"
      },
      { charset: "utf-8" },
      { property: "og:title", content: "Peter' Space" },
      { property: "og:site_name", content: "Peter' Space" },
      { property: "og:type", content: "website" },
      { property: "og:url", content: "https://peter.space" },
      {
        property: "og:image",
        content: "https://i.imgur.com/Dcz2PGx.jpg"
      },
      {
        property: "og:description",
        content:
          "Peter Samir's Web Portfolio Vue Vue.js Nuxt Nuxt.js HTML CSS Vuetify Axios GraphQL JavaScript Web Developer Front-End Frontend Designer App Responsive"
      }
    ]
  },
  data() {
    return {
      dialog: false,
      projects: [
        {
          title: "SmartCheck",
          demo: "https://www.alltrustnetworks.com/check-cashing-solutions/",
          tech: [
            "VueJS",
            "JavaScript",
            "SCSS",
            "HTML"
          ],
          poster: "https://smartcheck.alltrustnetworks.com/assets/images/svg/smartcheck-color.svg"
        },
        {
          title: "SME",
          demo: "https://digital.banquemisr.com/sme/",
          tech: [
            "Angular",
            "TypeScript",
            "SCSS",
            "HTML"
          ],
          poster: "https://digital.banquemisr.com/sme/Banque_Misr_Logo_left.17644c5a22b55808.svg"
        },
        {
          title: "YOLO Cosmetics E-commerce",
          demo: "https://yolo-cosmetics.com/en/home/",
          tech: [
            "Wordpress",
            "Migs payment gateway",
            "JavaScript",
            "SCSS",
            "HTML"
          ],
          poster: "https://yolo-cosmetics.com/wp-content/webp-express/webp-images/uploads/2021/12/Webp.net-resizeimage11.png.webp"
        },
        {
          title: "Raya Chat Agent",
          demo: "https://raya.notchagent.com:245/",
          tech: [
            "ReactJS",
            "JavaScript",
            "SCSS",
            "HTML"
          ],
          poster: "https://notchnco.com/images/RAYA22.png"
        },
        {
          title: "Alkuttab Educational App",
          demo: "https://alkuttab.io/",
          tech: [
            "VueJS",
            "JavaScript",
            "SCSS",
            "HTML"
          ],
          poster: "https://alkuttab-qc.s3.amazonaws.com/profile_pictures/logo_1_1.png"
        },
        {
          title: "Wrapup",
          demo: "https://efghermesresearch.com/wrapup/highlights.php",
          tech: [
            "PHP",
            "JavaScript",
            "SCSS",
            "HTML"
          ],
          poster: "https://efghermesresearch.com/wrapup/assets/layouts/layout5/img/logo.png"
        },
        {
          title: "Promote Energy Website",
          demo: "https://promote-energy.com/",
          tech: [
            "Wordpress",
            "JavaScript",
            "SCSS",
            "HTML"
          ],
          poster: "http://promote-energy.com//wp-content/uploads/2019/01/logo-4-e1547413539204.png"
        },
        {
          title: "On Board Website",
          demo: "https://onboardhc.com/",
          tech: [
            "Wordpress",
            "JavaScript",
            "SCSS",
            "HTML"
          ],
          poster: "https://onboardhc.com/wp-content/themes/tutorial/img/logo-in-dark.png"
        },
        {
          title: "Retail Code Website",
          demo: "https://retailcodeme.com/",
          tech: [
            "Wordpress",
            "JavaScript",
            "SCSS",
            "HTML"
          ],
          poster: "https://retailcodeme.com/wp-content/themes/rc/images/logo.png"
        },
        {
          title: "CMCServe compliance engine",
          demo: "https://cmcserv.com/",
          tech: [
            "Angular",
            "Typescript",
            "Laravel",
            "PHP",
            "SCSS",
            "HTML"
          ],
          poster: "https://d1muf25xaso8hp.cloudfront.net/https%3A%2F%2F89a66e5b82c0030b517cc64cad9664c1.cdn.bubble.io%2Ff1660633571675x545517476023001500%2FCMCSERV%2520Logo%2520Ramzy.png?w=256&h=60&auto=compress&dpr=1&fit=max"
        },
      ]
    };
  }
};
</script>

<style  scoped></style>