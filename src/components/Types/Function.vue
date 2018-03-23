<<template>
  <div>
    <h5>Parameters:</h5>
    <div v-for="item in item.Parameter">
      <span class="code">{{ item.$.Name }}</span>
      ({{ item.$.Type }})
    </div>
    <h5>Return type:</h5>
    <div v-for="item in item.ReturnType">
      <span class="code">{{ item.$.Type }}</span>
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
