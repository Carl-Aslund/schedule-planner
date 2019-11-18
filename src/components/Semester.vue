<template>
<div class="semester">
  <p class="ref">{{ semname }}</p>
  <div v-for="course in courses" v-bind:key="course">
    <Course :name="course.name"
            :category="course.category"
            :credits="course.credits"
            :notes="course.notes"></Course>
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
    courses: Object
  },
  computed: {
    total() {
      let creditCounts = this.courses.map((item) => item.credits)
      return creditCounts.reduce((total, count) => total+count)
    }
  }
}
</script>

<style scoped>
.semester {
  width: 12%;
}

.total, .ref {
  font-size: 32px;
  font-family: sans-serif;
  margin: 3%;
  text-align: center;
}
</style>