<<template>
  <div>
    <div class="members">
      <h5>Members:</h5>
      <div v-for="member in item.Member">
        <span class="code">{{ member.$.Name }}</span>
        <span class="code">({{ member.$.Value }})</span>
      </div>
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
