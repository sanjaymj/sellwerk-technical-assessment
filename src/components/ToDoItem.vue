<template>
  <div v-bind:class="{ item__opacity: this.status === 'DONE' }" class="stack-small">
    <span>{{description}}</span>
    <div class="btn-group">
      <button type="button" class="btn btn__secondary">
        Edit
      </button>
      <button type="button" class="btn btn__primary">
        Complete
      </button>
      <button type="button" class="btn btn__danger">
        Delete
      </button>
    </div>
  </div>
</template>

<script>

export default {
  components: {
  },
  props: {
    description: { required: true, type: String },
    status: { required: true, type: String },
    id: { required: true, type: String }
  },
  
  computed: {
    isDone() {
      return this.status === "DONE";
    }
  }
};
</script>

<style>
.item__opacity {
    opacity: 0.3;;
}
</style>
