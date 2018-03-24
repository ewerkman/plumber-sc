<<template>
  <div>
    <div class="inputparameters">
      <h5>Input Parameters:</h5>
      <div v-for="item in item.Parameter">
        <span class="code">{{ item.$.Name }}</span>
        <span class="code">({{ item.$.Type }})</span>
      </div>
    </div>
    <div class="returntype">
      <h5>Return type:</h5>
      <div v-for="item in item.ReturnType">
        <span class="code">{{ item.$.Type }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["item"]
};
</script>

<style>

</style>
