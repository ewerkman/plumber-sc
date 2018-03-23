<<template>
<div>

    <div v-if="!block">
      <b-row>
      </b-row>
    </div>
    <div v-else class="block">
        <b-row>
            <b-col>
        <span class="namespace">{{ block.Namespace }}</span>
        <h3>{{ block.Name }}</h3>

        <div v-bind:title="block.Receives | prettyReceives">
            <i class="fa fa-sign-in" aria-hidden="true"></i> {{ block.Receives | prettyClrType }}
        </div>
        <div v-bind:title="block.Returns | prettyReturns">
            <i class="fa fa-sign-out" aria-hidden="true"></i> {{ block.Returns | prettyClrType }}
        </div>
        </b-col>
        </b-row>
        <b-row class="mt-3">
            <b-col>
        <h4>Used in the following pipelines:</h4>
        <ul>
            <li v-for="pipeline in pipelines">
                <router-link :to="{ name: 'pipelines', params: { pipelineid: getPipelineName(pipeline) }}">
                {{ pipeline.Name }}
                </router-link>
            </li>
        </ul>
            </b-col>
        </b-row>
    </div>
</div>
</template>

<script>
import { prettyClrType } from "../filters/clrTypes";
import { prettyReceives } from "../filters/titles"
import { prettyReturns } from "../filters/titles"

export default {
  props: ["blockname"],
  data() {
    return {
      pipelines: []
    };
  },
  filters: {
    prettyClrType,
    prettyReceives,
    prettyReturns
  },
  computed: {
    block: function() {
      var selectedBlock = null;
      if (this.blockname) {
        selectedBlock = this.$store.state.blocks.find(block => {
          return this.blockname === `${block.Namespace}.${block.Name}`;
        });
        this.pipelines = this.$store.getters.getPipelinesForBlock(
          this.blockname
        );
      }
      return selectedBlock;
    }
  },
  mounted() {},
  beforeUpdate() {},
  methods: {
    getPipelineName: pipeline => {
      return `${pipeline.Namespace}.${pipeline.Name}`;
    }
  }
};
</script>

<style>
.block {
  background-color: #e1bee7 !important;
  padding: 10px;
  -webkit-border-radius: 8px;
  -moz-border-radius: 8px;
  border-radius: 8px;
}
</style>
