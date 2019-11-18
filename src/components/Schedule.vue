<template>
<div class="schedule">
  <div v-for="semester in semesters" :key="semester">
    <Semester :semname="semester.name" :courses="semester.courses"></Semester>
  </div>
</div>
</template>

<script>
import states from "../assets/sems.json";
import Semester from "./Semester.vue";
export default {
  name: 'Schedule',
  components: {
    Semester
  },
  computed: {
    semesters() {
      return states.semesters
    }
  }
}
</script>

<style scoped>
.semester {
  margin: 1%;
  float: left;
}
</style>