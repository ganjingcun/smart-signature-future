<template>
    <div class="WangEditor" >
        <div ref="editor" style="text-align:left"></div>
        <button v-on:click="getContent">查看内容</button>
    </div>
</template>

<script>
import E from 'wangeditor';

export default {
  name: 'WangEditor',
  data() {
    return {
      editorContent: '',
    };
  },
  methods: {
    getContent() {
      alert(this.editorContent);
    },
  },
  mounted() {
    const editor = new E(this.$refs.editor);
    editor.customConfig.onchange = (html) => {
      this.editorContent = html;
    };
    editor.create();
  },
};
</script>

<style scoped>
.WangEditor {
        margin: auto;
        width: 100%;
        height: 580px;
}
</style>
