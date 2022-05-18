<template>
  <v-app>
    <v-container>
      <v-row class="text-center">
        <v-col cols="12">
          <v-img
            :src="logo"
            class="my-3"
            contain
            height="200"
          />
        </v-col>
  
        <v-col class="mb-4">
          <h1 class="display-2 font-weight-bold mb-3">
            Vite + TypeScript + Vue(Vuetify)サンプル
          </h1>
        </v-col>
      </v-row>

      <v-row class="text-center">
        <v-col class="mb-4">
          <p class="display-2 font-weight-bold mb-3">
            COUNT : {{counter}}
          </p>
        </v-col>
      </v-row>

      <v-row class="text-center">
        <v-col class="mb-4">
          <v-btn 
            color="primary"
            :disabled="isLimit"
            @click="countUp()"
          >
            COUNT UP
          </v-btn>
        </v-col>
      </v-row>

    </v-container>
  </v-app>
</template>

<script lang='ts'>
import { defineComponent } from 'vue'

// Logo
import logo from '../assets/logo.svg'

export default defineComponent({
  name: 'HelloWorld',

  data () {
    return {
      logo,
      counter: 0,
      isLimit: false,
    }
  },

  methods: {
    countUp: function() {
      if (this.counter > 99) {
        this.isLimit = true;
        return;
      }

      this.counter++;
    }
  }
})
</script>
