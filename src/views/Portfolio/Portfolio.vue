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
          poster: "data:image/png;base64,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"
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
          poster: "https://media.licdn.com/dms/image/C4E0BAQF_Wm4-1K3aEg/company-logo_200_200/0/1644719992763?e=2147483647&v=beta&t=aNezMhH6Sr2jsCQwsxxTmsSXC0K7HUEbD6kHJSgPXUg"
        },
        {
          title: "Notchnco RSVP",
          demo: "https://notchnco.rsvp/",
          tech: [
            "PHP",
            "JavaScript",
            "SCSS",
            "HTML"
          ],
          poster: "https://notchnco.rsvp/assets/img/logo.svg"
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
          poster: "https://media.licdn.com/dms/image/C560BAQH598LTDXYTlA/company-logo_200_200/0/1519862778474?e=2147483647&v=beta&t=cHzSSn24nb0C3JJcWCKzYJOO3UJTQDgCW-qAn35d_CE"
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