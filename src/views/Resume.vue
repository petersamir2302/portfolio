<template>
  <v-layout row justify-center wrap class="mt-4 pt-2">
    <v-flex xs12 sm12 md5 lg6 xl6 class="mt-4 pt-2">
      <h2 class="mb-4 pl-4 pt-2">Education</h2>
      <v-card-text class="py-0">
        <v-timeline align-top dense>
          <v-timeline-item color="green" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold green--text">09/2013 -</div>
                <div class="caption font-weight-bold green--text">06/2017</div>
              </v-flex>
              <v-flex class="pl-2">
                <a class="green--text text-decoration-none" href="https://www.futureacademyegypt.com/en/home"
                  target="_blank">
                  <strong>Bechalor of Computer science</strong>
                  <div class="caption mb-2">Future academy</div>
                </a>
              </v-flex>
            </v-layout>
          </v-timeline-item>

          <v-timeline-item color="green" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold green--text">Dec 2020</div>
              </v-flex>
              <v-flex class="pl-2">
                <a class="green--text text-decoration-none" href="https://graduation.udacity.com/confirm/7STV5FUQ"
                  target="_blank">
                  <strong>
                    FrontEnd Advanced Nanodegree program
                  </strong>
                  <div class="caption mb-2">Udacity with the support of eg-fwd initiative.</div>
                </a>
              </v-flex>
            </v-layout>
          </v-timeline-item>
        </v-timeline>
      </v-card-text>
    </v-flex>
    <v-flex xs12 sm12 md4 lg6 xl6 class="mt-4 pt-2">
      <h2 class="mb-4 pl-4">Experience</h2>
      <v-card-text class="py-0">
        <v-timeline align-top dense>
          <v-timeline-item color="green" small v-for="exp in expereinces">
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold green--text">{{ exp.start_date }} -</div>
                <div class="caption font-weight-bold green--text">{{ exp.end_date }}</div>
              </v-flex>
              <v-flex class="pl-2">
                <a class="green--text text-decoration-none" v-bind:href="exp.link"
                  target="_blank">
                  <strong>{{ exp.title }}</strong>
                  <div class="caption mb-2">{{ exp.company }}</div>
                </a>
              </v-flex>
            </v-layout>
          </v-timeline-item>
        </v-timeline>
      </v-card-text>
    </v-flex>
    <v-layout row wrap class="mt-4 pt-2 d-flex justify-content-between">
      <v-flex xs12 sm12 md4 lg5 xl5 class="mx-2 pt-4">
        <h2>
          <span>Front-End </span>
          <span class="green--text">Skills</span>
        </h2>
        <br>
        <strong>HTML/CSS</strong>
        <v-progress-linear v-model="buffer6" :buffer-value="bufferValue" color="orange" height="16"></v-progress-linear>
        <strong>JavaScript</strong>
        <v-progress-linear v-model="buffer6" :buffer-value="bufferValue" color="yellow" height="16"></v-progress-linear>
        <strong>VUE/NUXT</strong>
        <v-progress-linear v-model="buffer5" :buffer-value="bufferValue" color="green" height="16"></v-progress-linear>
        <strong>ReactJS</strong>
        <v-progress-linear v-model="buffer3" :buffer-value="bufferValue" color="blue" height="16">
        </v-progress-linear>
        <strong>Angular2+</strong>
        <v-progress-linear v-model="buffer4" :buffer-value="bufferValue" color="red" height="16">
        </v-progress-linear>
      </v-flex>
      <v-flex xs12 sm12 md4 lg5 xl5 class="mx-2 pt-4">
        <h2>
          <span>Back-End </span>
          <span class="green--text">Skills</span>
        </h2>
        <br>
        <strong>PHP</strong>
        <v-progress-linear v-model="buffer6" :buffer-value="bufferValue" color="purple" height="16">
        </v-progress-linear>
        <strong>Laravel</strong>
        <v-progress-linear v-model="buffer5" :buffer-value="bufferValue" color="red" height="16">
        </v-progress-linear>
        <strong>MySql</strong>
        <v-progress-linear v-model="buffer5" :buffer-value="bufferValue" color="blue" height="16">
        </v-progress-linear>
      </v-flex>
      <div class="mt-4 pt-2">
        <v-btn href="https://drive.google.com/file/d/11XhpU4Uo-D_DAvuLdVwVbj6UzxTw47Sc/view?usp=sharing"
          target="_blank" color="green" dark large>
          Download Resume
          <v-icon right dark>fas fa-file-download</v-icon>
        </v-btn>
      </div>
    </v-layout>
  </v-layout>
</template>

<script>
export default {
  metaInfo: {
    title: "Resume",
    titleTemplate: "%s ← Peter's Space",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        name: "description",
        content:
          "Vue NUXT HTML CSS JavaScript Design Adobe XD Photoshop Coding Skills Resume Work Web Developer Front-End"
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
          "Vue NUXT HTML CSS JavaScript Design Adobe XD Photoshop Coding Skills Resume Work Web Developer Front-End"
      }
    ]
  },
  data() {
    return {
      value: 0,
      buffer1: 0,
      buffer2: 0,
      buffer3: 0,
      buffer4: 0,
      buffer5: 0,
      buffer6: 0,
      bufferValue: 100,
      interval: 0,
      expereinces: [
        {
          start_date: '10/2020',
          end_date: 'present',
          link: 'https://flairstech.com/',
          title: 'Senior FrontEnd Engineer',
          company: 'Flairstech'
        },
        {
          start_date: '01/2019',
          end_date: '09/2020',
          link: 'https://www.banquemisr.com/en/home',
          title: 'Senior software Engineer',
          company: 'Mckinsey & Company- Banque Misr - Asset technology'
        },
        {
          start_date: '06/2018',
          end_date: '01/2019',
          link: 'https://viral21.com',
          title: 'Web Development Technical Lead',
          company: 'viral21'
        },
        {
          start_date: '03/2018',
          end_date: '06/2018',
          link: 'http://4tress.agency/',
          title: 'Senior Software Engineer',
          company: 'Fortress Agency'
        },
        {
          start_date: '01/2017',
          end_date: '02/2018',
          link: 'https://www.facebook.com/lampaegypt/',
          title: 'Full-Stack developer',
          company: 'Lampa Digital Solutions'
        },
        {
          start_date: '06/2015',
          end_date: '01/2017',
          link: '#',
          title: 'Android developer',
          company: 'Freelance'
        }
      ]
    };
  },
  mounted() {
    this.startBuffer();
  },

  beforeDestroy() {
    clearInterval(this.interval);
  },

  methods: {
    startBuffer() {
      this.interval = setInterval(() => {
        this.buffer1 = 20;
        this.buffer2 = 40;
        this.buffer3 = 60;
        this.buffer4 = 80;
        this.buffer5 = 90;
        this.buffer6 = 95;
      }, 800);
    }
  }
};
</script>
<style ></style>

