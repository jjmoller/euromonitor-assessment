<template>
  <div class="signature">
    <img src="https://styleguide.euromonitor.com/assets/images/brand-guide/passport/the-signature/vertical-lockup.png">
  </div>
  <h1>Price of Converse Chuck Taylor All Star High School</h1>
  <span class="subheading">Graphed over a time period from 2015-2016</span>
  <span class="subheading">Price depicted is the average between three retailers</span>
  <div id="chart-container">
    <Line :data="data" :options="options" />
  </div>
  <div class="author">
    <span>Visualisation by Juan Moller</span>
  </div>
</template>

<script lang="ts">
import {
  Chart as ChartJS,
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend
} from 'chart.js'
import { Line } from 'vue-chartjs'
import * as chartConfig from './components/Chart.vue'

ChartJS.register(
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
  Title,
  Tooltip,
  Legend
)

export default {
  name: 'App',
  components: {
    Line
  },
  data() {
    return chartConfig
  }
}
</script>

<scss>
  body {
    display: absolute;
    margin: auto;

    #app {
      display: flex;
      flex-direction: column;

      .signature {
        position: fixed;
        top: 2rem;
        left: 3rem;

        img {
          width: 128px;
          height: auto;
        }
      }

      .subheading {
        &:nth-of-type(2) {
         margin-bottom: 1em;
         color: #787878;
        }
      }

      #chart-container {
        max-width: 800px;
        height: 400px;
      }

      .author {
        position: relative;
        top: 2rem;
        right: 0;
        text-align: right;
        color: #787878;
      }

      @media (max-width: 1200px) {
        .signature {
          position: static;
          margin: 0 auto;
          padding-bottom: 1rem;
        }
      }
    }
  }
</scss>