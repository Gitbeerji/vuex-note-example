<template lang="html">
  <div class="item">
    <div class="meta">
      {{ updated(entity) }}
    </div>
    <div class="content">
      <div class="header" v-on:click=" open = !open ">
        {{ header(entity) || '新建笔记' }}
      </div>
      <div class="extra">
        <editor
          v-if="open"
          v-bind:entity="entity"></editor>
       <div class="ui form">
         <div class="filed">
           {{ words(entity) }} 字
           <i class="right floated outline icon trash alternate" v-on:click="destory(entity)"></i>
         </div>
       </div>
      </div>
    </div>
  </div>
</template>

<script>
import Editor from './Editor'
import { mapGetters, mapActions } from 'vuex'

export default {
  computed: {
    ...mapGetters([
      'updated',
      'words',
      'header'
    ])
  },
  data () {
    return {
      open: false
    }
  },
  props: [
    'entity'
  ],
  components: {
    Editor
  },
  methods: {
    ...mapActions([
      'destory'
    ])
  }
}
</script>

<style lang="css" scoped>
</style>
