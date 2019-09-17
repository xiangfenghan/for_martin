<template>
  <div>
    <b-list-group>
      <div v-for="candidate in candidates" v-bind:key="candidate.id">
        <b-list-group-item v-if="!candidate.saved && !candidate.rejected">
          <Candidate v-bind:candidate="candidate" />
          <div class="btn-group">
            <Button v-on:clickOnBtn="$emit('clickOnBtn', {'id': candidate.id, 'event': 'save'})" @created="handleCreate" label="Save" variant="success"/>
            <Button v-on:clickOnBtn="$emit('clickOnBtn', {'id': candidate.id, 'event': 'reject'})" @created="handleCreate" label="Reject" variant="danger" />
          </div>
        </b-list-group-item>
      </div>
    </b-list-group>
  </div>
</template>

<script>
import Candidate from './Candidate.vue';
import Button from './Button.vue';

export default {
  name: 'Candidates',
  components: {
    Candidate,
    Button
  },
  props: ["candidates"],
  methods: {
    handleCreate() {
      // console.log('Child has been created.');
    }
  },
  data() {
        return {
            props: {  }
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .list-group-item {
    display: flex;
    padding: 0;
    border-top: none; 
    border-left: none;
    border-right: none;
    border-radius: 0;
  }

  .btn-group {
    justify-self: flex-end;
    padding: 1.25rem;
    margin-left: auto;
  }
</style>
