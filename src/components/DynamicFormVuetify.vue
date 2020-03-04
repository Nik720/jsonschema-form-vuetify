<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <h2>Vuetify form</h2>
        <v-form v-model="formValid">
          <v-jsonschema-form v-if="schema" :schema="schema" :model="dataObject" :options="options" @error="showError" @change="showChange" @input="showInput" />
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  import VJsonschemaForm from '@koumoul/vuetify-jsonschema-form/lib/index.vue'
  export default {
    name: 'DynamicFormVuetify',
    components: {VJsonschemaForm},
    data: () => ({
      schema: {
        "type": "object",
        "required": [
            "firstName",
            "lastName"
        ],
        "properties": {
            "start time": {
              "name": "startTime",
              "type": "string",
              "format": "time",
              "description": "\nThe person's first name.\n\nThis description can be a long text with markdown content.\n\n  - a list item\n  - another one\n  ",
              "x-class": "sm6 pr-4"
            },
            "end time": {
              "type": "string",
              "format": "time",
              "description": "The person's last name.",
              "x-class": "sm6"
            },
            "title": {
              "description": "A longer text for the description.",
              "type": "string"
            },
            "description": {
              "description": "A longer text for the description.",
              "type": "string",
              "maxLength": 2000
            },
            "Tags": {
              "title": "tags",
              "type": "array",
              "description": "The values are simple strings coming from a oneOf choice with 'const' and 'title' attributes and put into an array.",
              "items": {
                "type": "string",
                "oneOf": [
                  {
                    "const": "html",
                    "title": "HTML"
                  },
                  {
                    "const": "css",
                    "title": "CSS"
                  },
                  {
                    "const": "js",
                    "title": "JS"
                  }
                ]
              }
            },
        }
      },
      dataObject: {},
      formValid: false,
      options: {
        debug: false,
        disableAll: false,
        autoFoldObjects: true
      }
    }),
    methods: {
      showError(err) {
        window.alert(err)
      },
      showChange(e) {
        console.log('"change" event', e)
      },
      showInput(e) {
        console.log('"input" event', e)
      }
    }
  }
</script>
