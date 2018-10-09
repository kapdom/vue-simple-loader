
# Vue Simple Loader
Add nice and simple loader to your project.
## Getting started
#### Requirements
Vue.js 2.+
#### Usage
    <template>
	    <div>
		    <p ref="html_elem">
		    </p>
		    <Loader  	              
		      :inProgress="showLoader"
		      :text=loaderText
		      :textColor=loaderTextColor
		      :setColor=loaderColors
		      :setHeight=loaderHeight
		      :setWidth=loaderWidth
		      :htmlElem=this.$refs.html_elem
		      >
		    </Loader>
	    </div>
    </template>
    <script>
	    import Loader from 'vue-simple-loader';
	    export default {
		    components: {  
			  Loader  
		     },
		     data:() => {
			    return {
				    showLoader: true,
				    loaderText: "Loading",
				    loaderTextColor: "#000",
				    loaderColors: {
					    firstCircle: "#8DED5A",
					    secondCircle: "#11CBD8"
				    }
				    loaderHeight: 200,
				    loaderWidth: 300,
			    }
		     }
	    }
    </script>
You don't need configure all this options. Only "**inProgress"** property is necessary to tell loader when should be displayed.
## Properties
``inProgress`` *Boolean*  - Show or hide loader.

``text`` *String* - Text to display.

``textColor`` *String* - Text colour.

``setColor`` *Object {firstCircle: 'color', secondCircle: 'color'}* - Use if you would like to change loader colors.

``setHeight`` *Number* - Loader height.

``setWidth`` *Number* - Loader width.

``htmlElem`` *HTMLElement* - As a parameter, pass reference to html element (like in example above). Use this
option if you would like to set loader dimensions exactly the same like other html element.
 
## Other info
Loader dimensions always automaticity set to parent height and width. Always you can set own size using properties like in example above.
## License
MIT