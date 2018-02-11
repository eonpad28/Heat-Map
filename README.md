# heat-map
<html>
   <head>
      <title>Highcharts Tutorial</title>
      <script src = "https://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js">
      </script>
      <script src = "https://code.highcharts.com/highcharts.js"></script>    
      <script src = "https://code.highcharts.com/highcharts-more.js"></script>    
      <script src = "https://code.highcharts.com/modules/heatmap.js"></script>  
   </head>
   
   <body>
      <div id = "container" style = "width: 550px; height: 400px; margin: 0 auto"></div>
      <script language = "JavaScript">
         $(document).ready(function() {
            var chart = {
               type: 'heatmap',
               marginTop: 40,
               marginBottom: 80
            };
            var title = {
               text: 'Fees Spenders Are Most Likely to Encounter'   
            };
            var xAxis = {
               categories: ['SelectAccount', 'Lively', 'Avidia Bank', 'The HSA Authority', 'HealthEquity', 'UMB Bank', 'HSA Bank', '', '', '']
            };
            var yAxis = {
               categories: ['Excess Contribution Request','Stop Payment Request','Overdraft / NSF Fee', 'Check Reimbursement Fee', 'ATM Withdrawal Fee', 'POS / Transaction Fees', 'Monthly Paper Statement Fee', 'Monthly Maintenance Fee'],
               title: null
            };
            var colorAxis = {
               min: 0,
               minColor: '#FFFFFF',
               maxColor: Highcharts.getOptions().colors[0]
            };
            var legend = {
               align: 'right',
               layout: 'vertical',
               margin: 0,
               verticalAlign: 'top',
               y: 25,
               symbolHeight: 280
            };
            var tooltip = {
               formatter: function () {
                  return '<b>' + this.series.xAxis.categories[this.point.x] +
                  '</b> sold <br><b>' +
                  this.point.value +
                  '</b> items on <br><b>' +
                  this.series.yAxis.categories[this.point.y] + '</b>';
               }
            };
            var series = [{
               name: 'Fees',
               borderWidth: 1,
               data: [[0,0,0],[0,1,0],[0,2,0],[0,3,0],[0,4,0],[0,5,0],[0,6,0],[0,7,0],[1,0,0],[1,1,0],[1,2,0],[1,3,0],[1,4,0],[1,5,0],[1,6,0],[1,7,0],[2,0,0],[2,1,25],[2,2,30],[2,3,0],[2,4,0],[2,5,0],[2,6,2],[2,7,0],[3,0,0],[3,1,38],[3,2,38],[3,3,0],[3,4,2.50],[3,5,0],[3,6,2],[3,7,0],[4,0,20],[4,1,20],[4,2,20],[4,3,2],[4,4,0],[4,5,0],[4,6,1],[4,7,3.95],[5,0,0],[5,1,20],[5,2,25],[5,3,15],[5,4,2.50],[5,5,0],[5,6,0.50],[5,7,2.50],[6,0,25],[6,1,25],[6,2,30],[6,3,10],[6,4,2],[6,5,2],[6,6,1.50],[6,7,2.50]],
               dataLabels: {
                  enabled: true,
                  color: '#000000'
               }
            }];

            var json = {};   
            json.chart = chart; 
            json.title = title;       
            json.xAxis = xAxis; 
            json.yAxis = yAxis; 
            json.colorAxis = colorAxis; 
            json.legend = legend; 
            json.tooltip = tooltip; 
            json.series = series;       

            $('#container').highcharts(json);
         });
      </script>
   </body>
   
</html>
