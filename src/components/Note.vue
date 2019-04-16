<template lang="html">
  <div class="item">
    <div class="meta">
      {{ 'updated' }}
    </div>
    <div class="content">
      <div class="header" v-on:click=" open = !open ">
        {{ entity.body || '新建笔记' }}
      </div>
      <div class="extra">
        <editor
          v-if="open"
          v-bind:entity="entity"></editor>
       <div class="ui form">
         <div class="filed">
           {{ 'words' }} 字
           <i class="right floated outline icon trash alternate"></i>
         </div>
       </div>
      </div>
    </div>
  </div>
</template>

<script>
import Editor from './Editor'

export default {
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

  }
}
</script>

<style lang="css" scoped>
</style>
