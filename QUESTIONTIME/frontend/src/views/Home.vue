<template>
  <div class="home">
    <div class="container">
      <div v-for="question in questions" :key="question.pk">
        <p class="mb-0">
          Posted by:
          <span class="author-name">{{ question.author }}</span>
        </p>
        <h2>{{ question.content }}</h2>
        <p>Answers: {{ question.answers_count }}</p>
      </div>
    </div>
  </div>
</template>

<style>
.author-name {
  font-weight: bold;
  color: #dc3545;
}
</style>

<script>
import { apiService } from "../common/api.service";

export default {
  name: "home",
  data() {
    return {
      questions: []
    };
  },
  methods: {
    getQuestions() {
      let endpoint = "api/questions/";
      apiService(endpoint).then(data => {
        this.questions.push(...data.results);
      });
    }
  },
  created() {
    this.getQuestions();
    console.log(this.questions);
  }
};
</script>
