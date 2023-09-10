<template>
  <v-container grid-list-xl>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-flex xs12 sm12 md12 lg12 xl12>
        <h2>
          <span>My</span>
          <span class="green--text">Services</span>
        </h2>
      </v-flex>
      <v-flex v-for="service in services" :key="service.src" xs6 sm3 md3 lg3 xl3>
        <v-card hover flat color="transparent" :style="{ 'cursor': 'context-menu' }">
          <v-card-title></v-card-title>
          <v-img :src="service.src" height="100" aspect-ratio="2.75" :alt="'Peter do ' + service.title"
            lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif" contain></v-img>
          <v-card-title class="justify-center">
            <v-flex text-xs-center subheading font-weight-bold>{{ service.title }}</v-flex>
          </v-card-title>
        </v-card>
      </v-flex>
      <v-flex xs12 sm12 md12 lg12 xl12>
        <h2>
          <span>My</span>
          <span class="green--text">Clients</span>
        </h2>
      </v-flex>

      <v-flex v-for="client in clients" :key="client.src" xs6 sm4 md3 lg2 xl2>
        <v-card flat :href="client.href" target="_blank" color="transparent">
          <v-hover>
            <v-img slot-scope="{ hover }" :src="client.src" :alt="client.name + ' logo'"
              lazy-src="https://cdn.dribbble.com/users/503653/screenshots/3143656/fluid-loader.gif" height="100"
              width="160" aspect-ratio="2.75" contain>
              <v-expand-transition>
                <div v-if="!hover" class="transition-fast-in-fast-out green v-img--reveal" style="height: 100%;"></div>
              </v-expand-transition>
            </v-img>
          </v-hover>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  metaInfo: {
    title: "Services",
    titleTemplate: "%s ← Peter's Space",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        name: "description",
        content:
          "Peter Samir's Services Web Development Video Editing Graphic Design Front-End Advetising"
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
          "Peter Samir's Services Web Development Video Editing Graphic Design Front-End Advetising"
      }
    ]
  },
  data() {
    return {
      clients: [
        {
          name: "Alltrust Networks",
          src: "https://www.alltrustnetworks.com/wp-content/uploads/2022/11/Untitled-1-1536x459.png",
          href: "https://www.alltrustnetworks.com/"
        },
        {
          name: "Banque Misr",
          src: "https://digital.banquemisr.com/sme/Banque_Misr_Logo_left.17644c5a22b55808.svg",
          href: "https://digital.banquemisr.com/sme/"
        },
        {
          name: "YOLO Cosmetics",
          src: "https://scontent.fcai15-1.fna.fbcdn.net/v/t39.30808-6/271639107_1757123021151889_5811921928920992909_n.jpg?_nc_cat=108&ccb=1-7&_nc_sid=a2f6c7&_nc_ohc=DPasM3B3ckIAX8t52lr&_nc_ht=scontent.fcai15-1.fna&oh=00_AfBg8p9bMhGC24-EvNE11udu0Vz7Jky15MILVLmanovQMA&oe=6501A9EF",
          href: "https://yolo-cosmetics.com/en/home/"
        },
        {
          name: "EFG Hermes",
          src: "https://efghermesresearch.com/wrapup/assets/layouts/layout5/img/logo.png",
          href: "https://www.efghermes.com/"
        },
        {
          name: "Raya Shop",
          src: "https://scontent.fcai15-1.fna.fbcdn.net/v/t39.30808-6/311676598_6188469404515358_5603991114483785978_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=a2f6c7&_nc_ohc=L5vH_4vVuC4AX9QBsQz&_nc_ht=scontent.fcai15-1.fna&oh=00_AfDxlZUTQAm98U863ru-xd2G8Js-XUpOldK4cY6ZgX3iIA&oe=650303C0",
          href: "https://www.rayashop.com/en"
        },
        {
          name: "On Board",
          src: "https://onboardhc.com/wp-content/themes/tutorial/img/logo-in-dark.png",
          href: "https://onboardhc.com/"
        },
        {
          name: "Retail Code",
          src: "https://scontent.fcai15-1.fna.fbcdn.net/v/t39.30808-6/302208612_418594340366489_1149431871006829960_n.png?_nc_cat=101&ccb=1-7&_nc_sid=a2f6c7&_nc_ohc=ynjVWaLLtqYAX_ZZMG5&_nc_ht=scontent.fcai15-1.fna&oh=00_AfAmp4W_Ni6Xed_U72jmGwVP7oOfSKR5U5UZhgdH-oLEmw&oe=6502B681",
          href: "https://retailcodeme.com/"
        },
        {
          name: "Lagoonie Tourism",
          src: "https://lagoonie.tours/images/lagoonie-tourism.png",
          href: "https://lagoonie.tours/"
        },
        {
          name: "Promote Energy",
          src: "http://promote-energy.com//wp-content/uploads/2019/01/logo-4-e1547413539204.png",
          href: "https://promote-energy.com/"
        },
        {
          name: "Tareeqi",
          src:
            "https://scontent.fcai15-1.fna.fbcdn.net/v/t39.30808-6/305811913_456345999882297_7257074558626388479_n.jpg?_nc_cat=102&ccb=1-7&_nc_sid=a2f6c7&_nc_ohc=8L8dxuEL0UoAX_wOzQJ&_nc_ht=scontent.fcai15-1.fna&oh=00_AfCeDjoYyhQ7RVh3eoFzyWl8gnFREZMhdujeMnj3gvZ_0w&oe=6502B1E8",
          href: "https://www.facebook.com/Tareeqiapp/"
        },
        {
          name: "Aklity",
          src: "https://scontent.fcai15-1.fna.fbcdn.net/v/t39.30808-6/300898437_591904269295121_2141620430753157277_n.jpg?_nc_cat=106&ccb=1-7&_nc_sid=a2f6c7&_nc_ohc=CA62Bnnqb2QAX-0KZAX&_nc_ht=scontent.fcai15-1.fna&oh=00_AfDfObkX5Nt7kUVaaqoopLXTCgbhRoot5MKyLjbHFWUP9A&oe=65025A02",
          href: "https://www.facebook.com/AklityMadinaty/"
        },
        {
          name: "Ag Voyage",
          src: "https://scontent.fcai15-1.fna.fbcdn.net/v/t39.30808-6/327266311_1148634235844659_791091715538714427_n.png?_nc_cat=105&ccb=1-7&_nc_sid=a2f6c7&_nc_ohc=um5WSc87CRgAX82pbgj&_nc_ht=scontent.fcai15-1.fna&oh=00_AfBR-uo-ZqhmzvELEBsw59y0h7TRlsASgvtjNJJYPCqfAw&oe=65027229",
          href: "https://www.facebook.com/AG.Voyagetravel"
        }
      ],
      services: [
        {
          src: "https://i.imgur.com/g74mGuU.png",
          title: "Web Design"
        },
        {
          src: "https://i.imgur.com/GvTt5GG.png",
          title: "Web Development"
        },
        {
          src: "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAABhlBMVEUAAADf6u////+qWT2AtPv03UWTTTZUkPmvWz9uwX3aSlSXTzecUjlSKx7k7/RfMiIhEQyFRjCepqlOUlPBys9mXmbp6enswy7740fn8/hpbnCIfCeyXUCHh4fKtznDJDB/hohFQEWPlpnV3+QUFhZ3fYCfkC2Pdhzy10BxxoB8sftJTU5WW10ZKxwdMiCFu/8mQioNFw9NhOTZ2dkuGBHO2N0zMzM9OT1ms3SpsbW1vsK2trZhYWGcnJxFJBkxVjg8aUSnTy/LurcHDBVPcJy5e2fLy8sfHx+yoTLYwz0VCwhfMSN2Pitbn2dRjlw8HxaqHyonQ3R2pugMFCMZIzE3TWxDXoNFd80iOmNYUVg1LApxXRZ2ayE/OBGReBzjuyxZURlOQA8mIwupmTDBoCakiCA2Xz5Lg1UsCAsUBAUSHxRKDhKJGiI4Cg2nKDEkBgmaNTvCQktiEhhYHiKHLjQ6Y6sZK0xWeq5kIiYqO1JYe6wTGiUzV5cUITpvpfomNUhqldGFWEqHnATOAAAQoklEQVR4nNWd+2MTVRbHJ502Tkg6pemDJG0xTRMlm0LBNEkfaWVXl7SQWlQeIqyiqwgoq/hgV8CV/c93MnNf87qvucnMfH9Bk8zj03Pu45x75o42FUXtg363rkVRvds/aEe6B5a0CMfu9yLBYXWLynj8kidsdxXx2YzXFDK5JU1YVMg30oFKKlKyhGuKATWtoZQLS5LwQDmgptWUgiHJEbbxfX1+/92VCHrwD3yq8bRFOULUyXzx5blzpWi68A482UAxmyMpQtjLfGXxnbswE1GlCw/B+cbS20gRAhN+dW6kqIAjQUTVdCPJnPQauJ+RBVkmtNyQBxGccV85nxwhGCm+ZZqwNHN8dHR0fIEJWTpyTllRzidHCJz0HIOwdLzytf3Drx8cMxmv27+sK+eTIyRbYbiTllaIse4By4gPxtYQ5QnfpRNeIAa60bBJb6/wz7GsHDCAcLm9f7BGFRehG9ByVTohGBQr1AvX9tvifwIP4fLBpsYpKiH0OkIPaW2x9E7AFQK1cCAI6SJs93mvwyI8DjjgPAWRn9DSptD0jiBc5jYfk7D0EPyo3u2hJADNiEKEmtYSsCMm3Be6Bp0QmnCwPhKcxR4rIxSZ4CHCiuAlaISl8yTg+vrA+d+jcCMKE2p9UcKW6BWohOB+e4AQ5HNWVBJqXTHCdXzk2dnhfMFYDZfOJlxxE4KzP2AT5inXNfTC/Ny2MKJDiPvQw2E+n9epKozRhln6pQ3DyM+ie23xE9aQ/Yb5bJZxFR5CMJGG7RB0Ne9EJrQp86fwdtd4CVFOYjabZQNyEKK+tEeakKcv5SC0GOfgDfMMjCNC2JvPjQyYLSggLME5W5cYLD4PBxQj1FeH4JQ8eQ8N5yRm+QC5CP+JGgtO+lOcVJBQNyAix7CoIROe5rl8lItwpvS15tUViglFCXUD9DccAaWG5jLzWT4TchEGTExp01JhQl13QmaNveKhwZHiBq8JdfZ4OIOnNUiUCY0MIfRT9oihgXhWs/myjKHQOblzwH16fFg6TzrqdaoF8RyBw4Xcd8GOmTWQOHO6GR4nRedmZTFmcBpjZYaRqIGdr8FPCIYMZnpOAysQwyy3kxqHziHfsHJtpZmjlYdfPVw5YvGhZru9yk0IuwPmgo4GYoo8t5OiJsBKRc3Y2dIST8YUxpNz/DaEfU2PSeiMFWcFCOFfT/uCIyPMJTR88jdD5ErM8QKMyIf8zRAPRqoQEeChiAnhXTAJhTsa69zQiNr9L6MuXFg+fIyyVnkhwht8nSmb0IpYClmPDlEv+fDbb745H0VH99G5Tr2XKVjXDiecU0NoGPOH17W4dP1wqIcxqiE09GHo1SeluRBGJYTG/NnYwLCuzwciqiBcjd+AjgKHSQWEOJSOXTcCEKMTGkmx4EhDP2J0wjw6fb1SK8ahWmWA7iHrQ4xMuIoyk8WNshmPyhlUW7at3IbGPPimu2Fm4pOZgcl4n59GJgRJyW4mTsCRWiFGjEoIW+GiMKDlXSoBzQ5siWoJYUfaKAvfULVSVIpYrjq34h0UoxLOypnQXBwdtaCSMAOM6A2tonqp0wwHwtZwAmqlViw7Y8ZZxe3QGStagk4KPaoi6tzUk4LVd8WEzpR7QexOzT1wuqpSG1YmT2iWPYLdJ5yDdBQCZsyJE5Y3dhubblWKnbKZKTfA2YoqnXTihOVOcE1Da7EMfVTQtxNGaNa0MKF58oZSwAkTmhxFKWoH/AkT8gD2VU9kJ0lYDndRLMU+OlnCDsK4cpHUUwJwV3ksMkFCE44Gl09yTVK5k/eRj6rtRydMmAE/frTz6NKjnWYOq5m7Ar4Tj7YSRAjnZBd37H9IxCayYQ0QskG5/xQTJAT9zEePnKZIAH6EmuGmc8QGs1a1zj2oTI4QTspyF51/L2Mj4hvv2keYPKWOvH3SeAjB8mPNDLhSDrrk1abXRy3TjAidOJilhVgJ9cJowannugcYxeR24D1+1/T4KCTc0zjUjZfQKAz7RfeVECFGOhkh7pBPc9uEmQ2eB7x5g8gxEer6X//mGdoQYa55Fd6l1aGSPgoJzV02YI938jNGQs/fGBNiqotuH4WEGbNTY2iXky8mwlzuEjjwfdgoL14mCe20KV0JJ2zuwEkMnJOeeAjViYOwvd/oL6y3Nitr+z5gWRs2T9yt6mozNsJ2Y0DeSdfz2BCNMLSn8Y0Ro/YYF2HA1g6VZQ5CIzvba3SCx0OAeJU450kzNsJA1diEWftjV4fuIczlLqMTWrObZBFqvTaDEMzaXIOyjzAHe5kr1sDvIRRbClVPiOv4w2wYFFt4CZtwpDjxEZqLVQEVg9GECJ88fvbs8RPyk31hQhRbYESnQ7Vn4E3HoCC2ENz5hDoJDyHUT/Hx3/9w821bN3945rWiiA1hfIijpuZH1gT0qv2fwJ5OfLghBkjPQIYQYsCfAZ6jf/2CvmiLEoKI4SkZ3Od2ck0ygrLjLb7YglRFmBAB/ujie/vMmTM/wa8GgoQoT/N+jszR2HzN78B3i/YPueJDUrQ4I4iwgCpFvvfyWXr+I/iyIUhI5Np2QnJtLedOTbEHbumLVUGECPBnP99IsMtpK8+XosyE0COpXWqGLoAQFRS6XBQDnnkOvu8LElKWZRzhtV/vCiNd1AHRS2gUyILXZzcDAHFbbKtdt+jSblRaHkKj4CkJ/f6mj88S6FHXhNeeaE/sj6l8yk3otqCjn/2A0E8HStcPx1Q+5SIMArSa43Mf4Rkw9MPHR6OvAS8sqp9z+wkNXDH58R/k5X/1EYKW6H66knMdv7Pb6LuW8fvOOv74CQnA39566+5nBOIvPkTn84YEoVOL4aqSVFvKFkroBrT03scY8ZnXU52PW1KEkxUiNLIewBHjC8zoQXR600GKCAnAu29h/Rt9+sSN+B+NVBoI5wMB/7L1ye/wc3eXmj7CYMBpS3fgN4/9XlpPIaEPcHrrJfzuGUH42P6kq55QcY2wj9APaCGixkiMi84HfdWE6muEPYRBgCTiT55pW00xobM2ujk+wmBAwlGfQMJfnf/fV0wI6i+VWpEkfC8E0EL8EPzkP4AQBMHLaglhFkBtjTCKZz4IB7R0G/zqOTktXUhBjXAZZyapgNPT4FfOkAGCyH3ZGuGQrPUYaoT5AaffgN/9hIf7gVyNsBVbVNwlwo1ix4KEaX+VNcIYkO6idlO8jYwIupnR7i7ChGHx4eYerhFW56MigNPTn0AjwixNXTRfmqEWYDbg9EFd/aWAi5L9KUyX2nl9QUKeRKi6+ktTDBAbEf7NhXPeE64Rxhb8lA9weusOeScLoiszk64RFgd0G7G7LE6Ic97aFVIkoDIfFetkoBF/x3eyLLx+SK5bNN0aQ42wFCARR6E6GyEbgh8/2rl62VMjvKO6RljGRUde+goexlrHj1wjXM5s0EXPPpZRYZyIBYMAx1UjnGGPKtRlXykXDQQcV43wAhOQ1idhC4q56C14GLmfogDhxGqEJQGnEaBr/y8BwknVCEu2wek/AwGlCL01wuRtR68RNtUCShGqqRFuBU9+sP3FXBQN9btTCghhAZSmXQqvEZarg8KAYhZEgL79PuUIA2qEnyqpESZasBAgzNEEbGgqS4gmMfBfJTXCkQFrPkBpwrHUCBOjjAjgFgIM2jpZljCHqqAcH1VRX0oAhiV+AwFRUBi4N7Q0ofoaYUkLTtMBIxDiDlVNjXBkC4bs8xmBMLdzEfqor4LW6kpDtl0IBcThtRxg2HuGBAgFa4QbblXpwb/ZqY8HcJI1wn0qIHpmQgRwmg0YuUb4qUCNcLgVzQ0pQGxBytsuRAhhjE8G97kdJ9bnqREO3ZJpnIByNcJNMkdj83HVCNdCbGhuoOde1APK5douney4AHf4aoRDVqTMDfROWiFAuCQKMr9KbEjUCF8ixVUj3ApNw6HHon+TsiAdUHWNMIIwfbm2sNpMUw4QWZC177wQ4VhqhJFDywFOdH8amRphfMLXcoAT3WNIoka4HBlQ/T5RZvg+UcJ8eO8secCx7fXVIrUgWSOMhh/tY2nACe/XJia4Q18kwMnuuScIiJr0ZwTgfwUBE0xoRgTcnk04IQ6wXsgB6nHsDCkCuBcVcDXZhDhn8YckYDy7e/JrQwYQR/SjbZMTTghXUD8VsaALMNmEZhVcllx9EQRMNCHuZSIAJpoQZkPIkF6sDSacEMUTr2UseKonnhD56IsILppowkzP18vwuyiyYIIJ0Wztt2iACSYEyd/P+AFvBwEmlhCZ8L2IgMklBCZ8LQ7oeXVAQglRoQ3yURYgLonV9TQQllseE/IDpoMQrWTDVshKyvyppYwQZw//eH2XDYjLKVNDmCF3x3txl9XLuABTQehdOf3zzRa3BVNC2NA8ukMB/AD+aJAewrK/7PT3T5iAtUZ6CDuaX7eCEQnAON7CIik4Y+v2uoQxXwUhvkFf18opIoS32lu3hNbutVs+vi0MWCzH8J4ZeUJQcjECXFq6h0aO21s0wDQRgiTpwAK8t2QJmfHlVgigXfiQHkI4Gg5sE460Dq7+gQsQP5y155SQpYcQdDQ9YEIC8Q5hRPyQ5B4ozkkNIZyU9hDg0hIshkIGxJvNQMA0EW5CwiUscP0PfR6Kn/NLDyEoDaoTJkR++mrLNiCK57UB3qU5PYSgPq9OmnBpCYz9byxCYv26RZTmpIcQVAEP7rkIgRFfbr18hQH7ZGlO2C67zsZYrKKviRI6l+q6AJfuOZ/eIkOlmrskMoTQNmKdZcIYCHtuwiVfvNH11B6FEepG/n/XWHxJIBx4ABve4rFQQl3/OxswZsJ7612PCbt7/lK61BCCYu76PYet54UbfVcLqK5KDyHzFUn1amD5ZooIq3S+Wkh5anoIqbt8t4qh1akhMb4lIwqh3PuA6Sr7Um0Qr0Yr3gx5H7BuFE6DnhnlJXQ2de8qziYGFN8O+vYeU7Q/jDPbu+4zob2jMBMxhBC9l1spYcbcdb0zZbNa7Gwwa1NBasD3Xm7wcnRZQnB4VfXSjNkp1qqNaq24u5jheycSrNJU/G51He7Y25Gq/qVDgu3eOH8Pdy/Iepth1Peugb35Fe5MJie4R7r31erRCYewrYx1n2cmH+qchoZiQt2Au9cP9gRfi6NOZXMP9kw+EyogxDsv96q7i3Fot4rnefNeEyp47xrrbUMT1Q0foAJC3bgRG5BX3rFQEWFyrDgbAKiEEHeo8crXjaojtCa38XvqbCEQkJ/QmTEcBhNa59GH25TLj1vbwxA+PHVmAE6BMoBthzAfdKZVPTsfj7KF1TA+AULwXEA4oX22eBRKZ8vxrQGTcM0hnLcJvbPbRMu5ceqz+DYh2LN8Lp8yQtjPsyNgsGf52bCuJqlaBa+WazMJp8Bq+jBlRoQBLAvQIjwA/XI2VUY0gAmDd05yE8Kt9Z2WGNabJkxotsVcerIIp2COz/HTVBgRvRYpfOMdkhAaUZvPp6Ql4leTMfsZmxC2RGjFuO+fKfxiK3YrdAinUCh9I5tPfFM0cMTT5QB0CJGfWjPdfD7RTdFYzeKXyLK7GUg41UYHaWfn5vOFuCaiTBXISIdjiRsRTl3TSG0fziVRs6euu9ynk3kISSumRHwWxIRTy6wV2mSpy9UGXYTEoJEC1Xj5XIRTy2tx3zinKtwG9BBajAc99vljVvdAhM9LOILcX9sMqANJguqDhbV9MTxL/wd1XgaK/4ayMgAAAABJRU5ErkJggg==",
          title: "Testing"
        },
        {
          src: "data:image/png;base64,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",
          title: "Deployment & Hosting"
        }
      ]
    };
  }
};
</script>
<style >
.v-img--reveal {
  opacity: 0.3;
}
</style>