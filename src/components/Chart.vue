<script>
export const data = {
  labels: [null, '2015', '2016', '2017', '2018', '2019'],
  datasets: [
    {
      label: 'All Star Low Tops',
      backgroundColor: '#34657f',
      borderColor: '#34657f',
      data: [null ,595, 607, 650, 667, 669]
    },
    {
      label: 'All Star High Tops',
      backgroundColor: '#00aed9',
      borderColor: '#00aed9',
      data: [null, 644, 702, 746, 737, 749]
    }
  ]
}
export const options = {
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    legend: {
      position: 'right' // Display the legend on the right side
    }
  },
  scales: {
    y: {
      grid: {
        display: true, // Hide the Y-axis grid lines
        drawBorder: false // Hide the Y-axis line
      },

      ticks: {
        maxTicksLimit: 5,
        Max: 800, // Specify the maximum value for the Y-axis labels
        suggestedMin: 550, // Specify the minimum value for the Y-axis labels
        precision: 0, // Set the number of decimal places for the tick labels

        callback: function(value, index, values) {
          return 'R' + value; // Add a dollar sign in front of each Y-axis value
        }
      }
    },
    x: {
      grid: {
        borderDash: [3, 3], 
        display: false, // Hide the Y-axis grid lines
        drawBorder: false // Hide the Y-axis line
      },
    }
  }
};
</script>
