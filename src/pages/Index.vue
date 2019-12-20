<template>
  <q-page class="" style="background:#15212a">
    <div class="row q-col-gutter-sm q-ml-xs q-mr-sm q-py-sm">
      <div class="col-lg-3 col-md-3 col-sm-12 col-xs-12">
        <gauge-chart></gauge-chart>
      </div>
      <div class="col-lg-3 col-md-3 col-sm-12 col-xs-12">
        <gauge-chart></gauge-chart>
      </div>
      <div class="col-lg-3 col-md-3 col-sm-12 col-xs-12">
        <gauge-chart></gauge-chart>
      </div>
      <div class="col-lg-3 col-md-3 col-sm-12 col-xs-12">
        <gauge-chart></gauge-chart>
      </div>

      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <bar-chart></bar-chart>
      </div>

      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <custom-pie-chart></custom-pie-chart>
      </div>

      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <stack-bar-chart></stack-bar-chart>
      </div>

      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <bubble-chart></bubble-chart>
      </div>

      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <scatter-chart></scatter-chart>
      </div>

      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <box-plot></box-plot>
      </div>

      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <doughnut-chart></doughnut-chart>
      </div>

      <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
        <radar-chart></radar-chart>
      </div>

    </div>
  </q-page>
</template>

<script>
import GaugeChart from "../components/GaugeChart";
import BarChart from "../components/BarChart";
import CustomPieChart from "../components/CustomPieChart";
import StackBarChart from "../components/StackBarChart";
import BubbleChart from "../components/BubbleChart";
import ScatterChart from "../components/ScatterChart";
import BoxPlot from "../components/BoxPlot";
import DoughnutChart from "../components/DoughnutChart";
import RadarChart from "../components/RadarChart";

export default {
  name: 'PageIndex',
    components: {
        RadarChart,
        DoughnutChart,
        BoxPlot,
        ScatterChart,
        BubbleChart,
        StackBarChart,
        CustomPieChart,
        BarChart,
        GaugeChart
    }
}
</script>
