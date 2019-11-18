<template>
<div class="semester">
  <p class="ref">{{ semname }}</p>
  <div v-for="course in courses" v-bind:key="course">
    <Course :name="course.name"
            :category="course.category"
            :credits="course.credits"
            :notes="course.notes"></Course>
  </div>
  <div v-for="n in blanks" v-bind:key="n">
    <Course :credits=0></Course>
  </div>
  <p class="total">{{ total }}</p>
</div>
</template>

<script>
import Course from "./Course.vue"
export default {
  name: "Semester",
  components: {
    Course
  },
  props: {
    semname: String,
    courses: Object,
    classes: Number
  },
  computed: {
    total() {
      let creditCounts = this.courses.map((item) => item.credits)
      return creditCounts.reduce((total, count) => total+count)
    },
    blanks() {
      return this.classes - this.courses.length
    }
  }
}
</script>

<style scoped>
.semester {
  min-width: 136px;
  width: 5%;
}

.total, .ref {
  font-size: 32px;
  font-family: sans-serif;
  margin: 1%;
  text-align: center;
}
</style>