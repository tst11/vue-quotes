<template>
  <div class="row">
      <div class="col-sm-12">
          <h3>Quotes Added</h3>
          <div class="progress">
              <div class="progress-bar" role="progressbar" :style="{'width': progress.value + '%'}" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">{{ progress.value/10 }}/10</div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
  props: ['progress']
}
</script>

<style>

</style>
