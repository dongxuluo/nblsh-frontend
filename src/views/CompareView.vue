<template>
  <code-diff
    :old-string="'12345'"
    :new-string="'3456'"
    file-name="test.txt"
    output-format="side-by-side"
  />
</template>
<script lang="ts">
import { defineComponent } from "vue";
import { CodeDiff } from "v-code-diff";

export default defineComponent({
  components: {
    CodeDiff,
  },
});
</script>
