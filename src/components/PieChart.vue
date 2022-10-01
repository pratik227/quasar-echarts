<template>
  <div>
    <q-card>
      <q-card-section class="text-h6">
        Pie Chart
      </q-card-section>
      <q-card-section>
        <ECharts ref="piechart"
          :option="options"
          class="q-mt-md"
          :resizable="true"
          autoresize style="height: 250px;"
        />
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
import ECharts from 'vue-echarts'
import * as echarts from 'echarts'

export default {
  name: "PieChart",
  components: {
    ECharts
  },
  data() {
    return {
      options: {
        tooltip: {
          trigger: 'item',
          formatter: '{a} <br/>{b}: {c} ({d}%)'
        },
        legend: {
          top: 'bottom',
          bottom: '5%',
          left: 'center'
        },
        series: [
          {
            name: 'Access source',
            type: 'pie',
            radius: ['40%', '70%'],
            center: ['50%', '35%'],
            avoidLabelOverlap: false,
            itemStyle: {
              borderRadius: 10,
              borderColor: '#fff',
              borderWidth: 2
            },
            label: {
              show: false,
              position: 'center'
            },
            emphasis: {
              label: {
                show: true,
                fontSize: '40',
                fontWeight: 'bold'
              }
            },
            labelLine: {
              show: false
            },
            data: [
              {value: 1048, name: 'Search Engine'},
              {value: 735, name: 'Direct access'},
              {value: 580, name: 'Email marketing'},
              {value: 484, name: 'Affiliate Advertising'},
              {value: 300, name: 'Video ad'}
            ]
          }
        ]
      }
    }
  }
}
</script>

<style scoped>

</style>
