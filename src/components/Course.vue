<template>
  <div class="course" v-bind:class="[category]">
    <p class="title">{{name}}</p>
    <p v-if="credits == 1">{{credits}} credit</p>
    <p v-else-if="credits != 0">{{credits}} credits</p>
    <p class="notes" v-if="notes != ''">{{notes}}</p>
    <br v-else/>
  </div>
</template>

<script>
export default {
  name: "Course",
  props: {
    name: String,
    category: String,
    credits: Number,
    notes: String
  }
}
</script>

<style scoped>
/* TODO */
.course {
  border: 1px solid black;
  padding: 3%;
  width: 100%;
  text-align: center;
  font-family: sans-serif;
  min-height: 65px;
}

p {
  margin: 2%;
}

.core {
  background-color: lightgray;
}

.hsa {
  background-color: cyan;
}

.major {
  background-color: goldenrod;
}

.elective {
  background-color: indianred;
}

.title {
  font-weight: bold;
}

.notes {
  font-style: italic;
}

</style>