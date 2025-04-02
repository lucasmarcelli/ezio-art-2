<template>
  <div class="markdown" v-html="parsed" />
</template>

<script>
// ===================================================================== Imports
import { unified } from 'unified'
import remarkParse from 'remark-parse'
import remarkRehype from 'remark-rehype'
import rehypeStringify from 'rehype-stringify'

export default {
  name: 'MarkdownParser',

  props: {
    markdown: { // markdown string
      type: String,
      required: true
    }
  },

  data() {
    return {
      parsed: null,
      processor: null
    }
  },

  created() {
    this.processor = unified()
      .use(remarkParse)
      .use(remarkRehype)
      .use(rehypeStringify)

    this.processor.process(this.markdown, (err, file) => {
      if (err) { console.log('error during parsing ', err) }
      if (file) { this.parsed = file }
    })

  }
}

</script>
