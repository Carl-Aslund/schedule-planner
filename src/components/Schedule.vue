<template>
<div class="schedule">
  <div v-for="semester in semesters" :key="semester">
    <Semester :semname="semester.name" :courses="semester.courses" :classes="classes"></Semester>
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
  data: function () {
    return {
        classes: 10
    };
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
  margin: 10px;
  float: left;
}
</style>