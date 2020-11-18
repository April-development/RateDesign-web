<script>
import { Line } from 'vue-chartjs'

export default {
  extends: Line,
  props: {
    data: {
      label: String,
      labels: [Number],
      values: [Number],
    },
  },
  data() {
    return {
      chartData: {
        labels: this.data.labels,
        datasets: [
          {
            label: this.data.label || 'График',
            data: this.data.values,
            backgroundColor: 'dodgerblue',
            borderColor: 'darkcyan',
            borderWidth: 1,
          },
        ],
      },
      options: {
        responsive: false,
        maintainAspectRatio: false,
      },
    }
  },
  mounted() {
    this.renderChart(this.chartData, this.options)
  },
}
</script>

<style>
body {
  color: dodgerblue;
}
</style>
