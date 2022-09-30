<template>
  <q-page class="">
    <div class="row q-col-gutter-sm q-ml-xs q-mr-sm q-py-sm">
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <line-chart></line-chart>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <bar-chart></bar-chart>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <pie-chart></pie-chart>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <scatter-chart></scatter-chart>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <dotted-bar-chart></dotted-bar-chart>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <guage-chart></guage-chart>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <boxplot></boxplot>
      </div>
      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <area-chart></area-chart>
      </div>
    </div>
  </q-page>
</template>

<script>
import {defineComponent} from 'vue'
import LineChart from "components/LineChart.vue";
import BarChart from "components/BarChart.vue";
import PieChart from "components/PieChart.vue";
import ScatterChart from "components/ScatterChart.vue";
import DottedBarChart from "components/DottedBarChart.vue";
import GuageChart from "components/GuageChart.vue";
import Boxplot from "components/BoxChart.vue";
import AreaChart from "components/AreaChart.vue";

export default defineComponent({
  name: 'IndexPage',
  components: {AreaChart, Boxplot, GuageChart, DottedBarChart, ScatterChart, PieChart, BarChart, LineChart}
})
</script>
