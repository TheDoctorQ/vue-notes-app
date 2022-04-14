<script>
export default {
  props: ["note", "selectedNoteId"],
  methods: {
    selectNote: function (note) {
      this.$emit("selectNote", note);
      console.log('in note selector')
    }
  }
}
</script>

<template>
  <div class="note-selector" v-bind:class="{ active: selectedNoteId === note.id }" v-on:click="selectNote(note)">
    <p class="note-selector-title">{{ note.body }}</p>
    <p class="note-selector-title">({{ selectedNoteId }}) {{ note.id }}</p>
    <p class="note-selector-timestamp">Timestamp here {{ note.timestamp }}</p>
  </div>
</template>