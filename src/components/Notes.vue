<template lang="html">
  <div class="ui container notes">
    <h4 class="ui horizontal divider header">
      <i class="paw icon"></i>
      Vue notes
    </h4>
    <div class="ui container">
      <div class="item">
          {{ amigo }}
      </div>
      <div class="">
        <input type="text" v-model="hello">
      </div>
    </div>
    <div class="ui container">
      <a
        class="ui right floated basic violet button"
        v-on:click="create">
        添加笔记
      </a>
    </div>
    <div class="ui divided items">
      <note
        v-for="entity in entities"
        v-bind:entity="entity"
        v-bind:key="entity.$loki">
      </note>
      <span
        class="ui small disabled header"
        v-if="!entities.length">
            还没有笔记，请按下 ‘添加笔记’ 按钮
      </span>
    </div>
  </div>
</template>

<script>
import Note from './Note'
import { mapGetters, mapActions } from 'vuex'

export default {
  data () {
    return {
      hello: ''
    }
  },
  created () {
    this.initial()
  },
  methods: {
    ...mapActions([
      'initial',
      'create'
    ])
  },
  computed: {
    ...mapGetters([
      'entities'
    ]),
    amigo: function () {
      return this.hello + 'bitch'
    }
  },
  components: {
    Note
  }
}
</script>

<style lang="css" scoped>
</style>
