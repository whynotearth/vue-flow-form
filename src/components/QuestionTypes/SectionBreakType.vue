<template>
  <div>
    <div class="f-content" v-if="question.content">
      <span class="section-text">{{ question.content }}</span>
    </div>
    <img v-if="question.image" class="f-content--image" :src="question.image" alt="">
  </div>
</template>

<script>
  /*
    Copyright (c) 2020 - present, DITDOT Ltd. - MIT Licence
    https://github.com/ditdot-dev/vue-flow-form
    https://www.ditdot.hr/en
  */

  import BaseType from './BaseType.vue'
  import { QuestionType } from '../../models/QuestionModel'
  import LanguageModel from '../../models/LanguageModel'

  export default {
    extends: BaseType,
    name: QuestionType.SectionBreak,
    beforeMount(){
      console.log(this.question);
    },
    methods: {
      onEnter() {
        this.dirty = true

        this._onEnter()
      },

      isValid() {
        return true
      }
    }
  }
</script>

<style scoped>
.f-content--image {
  margin-top: 16px;
  max-width: 100%;
}
</style>