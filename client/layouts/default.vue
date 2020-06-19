<template>
  <v-app dark>
    <v-system-bar
      app
      color="grey"
      :height="height"
      :lights-out="lightsOut"
      :window="window"
    >
      <v-icon>mdi-gmail</v-icon>
      <span>10 unread emails</span>
      <v-spacer></v-spacer>
      <v-icon>mdi-wifi-strength-4</v-icon>
      <v-icon>mdi-signal-cellular-outline</v-icon>
      <v-icon>mdi-battery</v-icon>
      <span>{{getTime}}</span>
    </v-system-bar>
    <v-navigation-drawer app></v-navigation-drawer>
    <v-app-bar
      app
      absolute
      dark
      hide-on-scroll
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Project</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main
      app
      style="height: 1000px;">
      <nuxt/>
    </v-main>

    <v-card>

      <v-footer
        color="dark grey lighten-1"
        padless
      >
        <v-row
          justify="center"
          no-gutters
        >
          <v-btn
            v-for="link in links"
            :key="link"
            color="white"
            text
            rounded
            class="my-2"
          >
            hello
          </v-btn>
          <v-col
            class="dark lighten-2 py-4 text-center white--text"
            cols="12"
          >
            {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
          </v-col>
        </v-row>
      </v-footer>

    </v-card>

  </v-app>
</template>
<script>
  export default {
    name: "MainInfo",
    data() {
      return {
        links: ["a", "b", "c"],
        height: 30,
        lightsOut: false,
        window: false,
        time: "12:00"

      }
    },
    computed: {
      getTime() {
        const now = new Date();
        let hour = String(now.getHours());
        let minute = String(now.getMinutes());
        hour = hour < 10 ? "0" + hour : hour;
        minute = minute < 10 ? "0" + minute : minute;
        return hour + ":" + minute;
      }
    },
  }
</script>
