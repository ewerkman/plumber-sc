<<template>
    <div v-if="property">
       <b class="code">{{ property.$.Name }}</b> : <span class="code">{{ property.$.Type }}</span>
    </div>
</template>

<script>
export default {
  props: ["property"]
};
</script>

<style>

</style>
