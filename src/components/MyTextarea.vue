<template>
  <div>
    <textarea :value="myData" @input="updateContent"/>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue, Model, Emit } from "vue-property-decorator";
import { EventEmitter } from "events";

@Component
export default class MyTextarea extends Vue {
  updateContent(event: any) {
    this.$emit("myDataChanged", event.target.value);
  }

  @Model("myDataChanged", { type: String })
  myData!: String;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
