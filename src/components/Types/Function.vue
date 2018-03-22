<<template>
  <div>
    <h5>Parameters:</h5>
    <dl v-for="item in item.Parameter">
      <dt>{{ item.$.Name }}</dt>
      <dd>{{ item.$.Type }}</dd>
    </dl>
    <h5>Return type:</h5>
    <div v-for="item in item.ReturnType">
      {{ item.$.Type }}
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
