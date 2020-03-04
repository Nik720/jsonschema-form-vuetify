<template>
  <div class="container">
    <div class="">
        <h2>Formio</h2>
      <formio :form="formschema" v-on:submit="formSubmission"></formio>
    </div>
  </div>
</template>

<script>
import { Form } from 'vue-formio';
export default {
  name: 'DynamicForm',
  components: { formio: Form },
  data() {
    return {
      formschema: {}
    }
  },
  created () {
    this.getFormConfig();
  },
  methods: {
    getFormConfig() {
      // this.axios.get("https://lvqgnlrsnqtqjhk.form.io/ideaform").then((response) => {
      //   this.formschema = response.data;
      // });

      this.formschema = {
          "components": [
              {
                  "clearOnHide": false,
                  "label": "Columns",
                  "input": false,
                  "tableView": false,
                  "key": "columns",
                  "columns": [
                      {
                          "components": [
                              {
                                  "autofocus": false,
                                  "input": true,
                                  "tableView": true,
                                  "inputType": "time",
                                  "format": "HH:mm",
                                  "label": "Start time",
                                  "key": "columnsStarttime",
                                  "placeholder": "",
                                  "prefix": "",
                                  "suffix": "",
                                  "defaultValue": "",
                                  "protected": false,
                                  "unique": false,
                                  "persistent": true,
                                  "hidden": false,
                                  "clearOnHide": true,
                                  "type": "time",
                                  "labelPosition": "top",
                                  "inputFormat": "plain",
                                  "tags": [],
                                  "conditional": {
                                      "show": "",
                                      "when": null,
                                      "eq": ""
                                  },
                                  "properties": {},
                                  "validate": {
                                      "required": true
                                  },
                                  "lockKey": true
                              }
                          ],
                          "width": 6,
                          "offset": 0,
                          "push": 0,
                          "pull": 0
                      },
                      {
                          "components": [
                              {
                                  "autofocus": false,
                                  "input": true,
                                  "tableView": true,
                                  "inputType": "time",
                                  "format": "HH:mm",
                                  "label": "End time",
                                  "key": "columnsEndtime",
                                  "placeholder": "",
                                  "prefix": "",
                                  "suffix": "",
                                  "defaultValue": "",
                                  "protected": false,
                                  "unique": false,
                                  "persistent": true,
                                  "hidden": false,
                                  "clearOnHide": true,
                                  "type": "time",
                                  "labelPosition": "top",
                                  "inputFormat": "plain",
                                  "tags": [],
                                  "conditional": {
                                      "show": "",
                                      "when": null,
                                      "eq": ""
                                  },
                                  "properties": {},
                                  "validate": {
                                      "required": true
                                  }
                              }
                          ],
                          "width": 6,
                          "offset": 0,
                          "push": 0,
                          "pull": 0
                      }
                  ],
                  "type": "columns",
                  "hideLabel": true,
                  "tags": [],
                  "conditional": {
                      "show": "",
                      "when": null,
                      "eq": ""
                  },
                  "properties": {}
              },
              {
                  "autofocus": false,
                  "input": true,
                  "tableView": true,
                  "inputType": "text",
                  "inputMask": "",
                  "label": "Title",
                  "key": "title",
                  "placeholder": "",
                  "prefix": "",
                  "suffix": "",
                  "multiple": false,
                  "defaultValue": "",
                  "protected": false,
                  "unique": false,
                  "persistent": true,
                  "hidden": false,
                  "clearOnHide": true,
                  "spellcheck": true,
                  "validate": {
                      "required": true,
                      "minLength": "",
                      "maxLength": "",
                      "pattern": "",
                      "custom": "",
                      "customPrivate": false
                  },
                  "conditional": {
                      "show": "",
                      "when": null,
                      "eq": ""
                  },
                  "type": "textfield",
                  "labelPosition": "top",
                  "inputFormat": "plain",
                  "tags": [],
                  "properties": {}
              },
              {
                  "autofocus": false,
                  "input": true,
                  "tableView": true,
                  "label": "Description",
                  "key": "description",
                  "placeholder": "",
                  "prefix": "",
                  "suffix": "",
                  "rows": 3,
                  "multiple": false,
                  "defaultValue": "",
                  "protected": false,
                  "persistent": true,
                  "hidden": false,
                  "wysiwyg": true,
                  "clearOnHide": true,
                  "spellcheck": true,
                  "validate": {
                      "required": true,
                      "minLength": "",
                      "maxLength": "",
                      "pattern": "",
                      "custom": ""
                  },
                  "type": "textarea",
                  "labelPosition": "top",
                  "inputFormat": "plain",
                  "tags": [],
                  "conditional": {
                      "show": "",
                      "when": null,
                      "eq": ""
                  },
                  "properties": {}
              },
              {
                  "autofocus": false,
                  "input": true,
                  "tableView": true,
                  "label": "Tag",
                  "key": "tag",
                  "placeholder": "",
                  "data": {
                      "values": [
                          {
                              "value": "css",
                              "label": "CSS"
                          },
                          {
                              "value": "html",
                              "label": "HTML"
                          },
                          {
                              "value": "js",
                              "label": "JS"
                          },
                          {
                              "value": "nodejs",
                              "label": "NODEJS"
                          }
                      ],
                      "url": "",
                      "resource": "",
                      "custom": ""
                  },
                  "dataSrc": "values",
                  "valueProperty": "",
                  "defaultValue": "",
                  "refreshOn": "",
                  "filter": "",
                  "authenticate": false,
                  "template": "<span>{{ item.label }}</span>",
                  "multiple": true,
                  "protected": false,
                  "unique": true,
                  "persistent": true,
                  "hidden": false,
                  "clearOnHide": true,
                  "validate": {
                      "required": true
                  },
                  "type": "select",
                  "labelPosition": "top",
                  "tags": [],
                  "conditional": {
                      "show": "",
                      "when": null,
                      "eq": ""
                  },
                  "properties": {}
              },
              {
                  "autofocus": false,
                  "input": true,
                  "label": "Submit",
                  "tableView": false,
                  "key": "submit",
                  "size": "md",
                  "leftIcon": "",
                  "rightIcon": "",
                  "block": false,
                  "action": "submit",
                  "disableOnInvalid": false,
                  "theme": "primary",
                  "type": "button"
              }
          ],
          "title": "ideaForm",
          "display": "form"
      }
    },
    formSubmission(evt) {
      console.log(evt)
    }
  },
}
</script>
