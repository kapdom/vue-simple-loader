
# Vue Simple Loader
Nice and simple loader to your project.
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
You don't need to configure all options. Only "**inProgress"** property is necessary to tell loader when it should be displayed.
## Properties
``inProgress`` *Boolean*  - Show or hide loader.

``text`` *String* - Text to display.

``textColor`` *String* - Text colour.

``setColor`` *Object {firstCircle: 'color', secondCircle: 'color'}* - Use this if you would like to change loader colors.

``setHeight`` *Number* - Loader height.

``setWidth`` *Number* - Loader width.

``htmlElem`` *HTMLElement* - As a parameter, pass reference to html element (like in example above). Use this
option if you would like to set loader dimensions exactly the same as other html element.
 
## Other info
Loader dimensions always automaticity set to parent height and width. You can always set own size using properties like in example above.
## License
MIT