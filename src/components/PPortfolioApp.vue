<template>
  <v-card flat color="transparent" max-width="350px">
    <v-card-title>
      <v-layout>
        <v-flex>
          <v-card
            elevation="5"
            style="border-radius: 20px"
            width="100px"
            height="100px"
          >
            <a v-bind:href=app.url target="_blank"><v-img :src="logo(app.logo)" /></a>
          </v-card>
        </v-flex>
        <v-flex xs7>
          <div>{{app.name}}</div>
        </v-flex>
      </v-layout>
    </v-card-title>
    <v-card-text>
      <div>{{app.description}}</div>
      <div class="title mt-2">Technologies Used</div>
      <v-layout>
        <template v-for="(tech, i) in app.technologies">
          <v-flex xs3 :key="i">
            <div class="text-center">
              <v-btn icon>
                <v-icon>{{tech.icon}}</v-icon>
              </v-btn>
              <div class="caption">{{tech.name}}</div>
            </div>
          </v-flex>
        </template>
      </v-layout>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    app: {
      type: Object,
      default: function() {
        return {};
      }
    }
  },
  methods: {
    logo(name) {
      return require("../assets/" + name);
    }
  }
};
</script>

<style>
</style>