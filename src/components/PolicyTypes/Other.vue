<<template>
    <div>
      <h3>{{ dataType }}</h3>
      <div v-html="getMarkedupJson(policy)">
      </div>
    </div>
</template>

<script>
import PolicyTypeMixin from "../../mixins/PolicyTypeMixin";

export default {
  mixins: [PolicyTypeMixin]
};
</script>

<style>
.json-markup {
  line-height: 17px;
  font-size: 13px;
  font-family: monospace;
  white-space: pre;
}
.json-markup-key {
  font-weight: bold;
}
.json-markup-bool {
  color: firebrick;
}
.json-markup-string {
  color: green;
}
.json-markup-null {
  color: gray;
}
.json-markup-number {
  color: blue;
}
</style>
