ChartJs
collection of some charts that can be used on the web (html)

<h2>Position Image over Chart</h2>
<p><b>In this tutorial we are going to describe how to position custom images over a chart.</b></p></br>
Here are the steps: </br>
<h2>Step1:</h2>
<p>Create a basic chart with required options and call chart.render() method to render the chart.</p>
</br>
************************ this code *********************************** 


    var chart = new CanvasJS.Chart("chartContainer",{
    	title :{
    		text: "Position Image over chart"
    	},
    	data: [{
    		type: "column",
    		dataPoints : [
    			{ label: "apple",  y: 10  },
    			{ label: "orange", y: 15  },
    			{ label: "banana", y: 25  },
    			{ label: "mango",  y: 30  },
    			{ label: "grape",  y: 28  }
    		]
    	}]
    });
    chart.render();

</br>
<h2>Step2:</h2>
<p>Append images to the Div element with class “canvasjs-chart-container”. This is a div created dynamically by CanvasJS inside the chartContainer created in Step 1. It holds all the Chart elements including canvas, tooltip, buttons etc.</p>
</br>


    $('img').attr('src', url)
            .attr("class", label)
            .css({"display": "none"})
            .appendTo($('#chartContainer>.canvasjs-chart-container'));

</br>
<h2>Step3:</h2>
<p>Get pixel co-ordinates where the images have to be placed using convertValueToPixel method. Once you have co-ordinates, images can be positioned relative to the div.</p>
</br>


    imageBottom = chart.axisX[0].bounds.y1;
    imageCenter = chart.axisX[0].convertValueToPixel(chart.data[0].dataPoints[0].x);
     
    image.css({"position": "absolute", 
               "display": "block",
               "top": imageBottom  - fruit.height(),
               "left": imageCenter - fruit.width()/2
             });  

