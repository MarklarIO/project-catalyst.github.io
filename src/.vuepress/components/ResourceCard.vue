<template>
  <v-card class="mx-auto" max-width="400" @click.stop="dialog = true">
    <v-card-title :style="'background-color:'+cardcolor+'; color:white'">
      {{title}}
    </v-card-title>
    <v-card-subtitle :style="'background-color:'+cardcolor+'; color:white'">
      {{subtitle}}
    </v-card-subtitle>
    <v-card-text>
      <Content/>
    </v-card-text>
  </v-card>
  <v-dialog v-model="dialog" scrollable max-width="80%">
    <v-card>
      <v-card-title :style="'background-color:'+cardcolor+'; color:white'">
        {{title}}
      </v-card-title>
      <v-card-subtitle :style="'background-color:'+cardcolor+'; color:white'">
        {{subtitle}}
      </v-card-subtitle>
      <v-card-text>
        {{text}}
      </v-card-text>
      <v-card-actions>
        <v-btn :href="linkurl" target="_blank">Go to Site</v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  props: {
    cardcolor: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    subtitle: {
      type: String,
      required: true,
    },
    linkurl: {
      type: String,
      required: true,
    },
    text: {
      type: String,
      required: true,
    }
  },
  data() {
    return {}
  }
}
</script>
