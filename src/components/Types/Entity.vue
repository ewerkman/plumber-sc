<<template>
  <div>
    <div v-if="item.Property && item.Property.length > 0">
      <h5>Properties</h5>
      <property name="item" v-for="item in item.Property" :key="item.$.Name" :property="item"></property>
    </div>
    <div v-if="item.NavigationProperty && item.NavigationProperty.length > 0">
      <h5>Navigation Properties</h5>
      <property name="item" v-for="item in item.NavigationProperty" :key="item.$.Name" :property="item"></property>
    </div>
  </div>
</template>

<script>
import Property from "@/components/Property";

export default {
  props: ["item"],
  components: { Property }
};
</script>

<style>

</style>
