<template v-on:load="forceRerender">
  <div class='tableauPlaceholder' :id='this.graphID' style='position: relative'>
        <noscript><a href='#'>
            <img alt=' ' src='https://public.tableau.com/static/images/KC/KCCOVID-19TestsPositivity/DailyNewCases/1_rss.png' style='border: none' /></a>
        </noscript>
        <object class='tableauViz'></object>
  </div>                
</template>

<script>

export default {
    props: {
    graphName: String,
    graphImage: String,
    graphID: String
  },
  methods: {
    toggle() {
        function addParams(obj, paramsObj){
            var vals;
            var p = document.createElement("PARAM");
          for(vals in paramsObj)
            {
                p.setAttribute(vals, paramsObj[vals])
            }
            obj.appendChild(p);
        }
        var divElement = document.getElementById(this.graphID);
        
                       var vizElement = divElement.getElementsByTagName('object')[0]; 
     vizElement.style.width='100%';vizElement.style.height=(divElement.offsetWidth*0.75)+'px';  
         var paramsObj = {"name":"toolbar", "value":"yes" };  
         addParams(vizElement, paramsObj);                
         var paramsObj = {"name":"host_url","value":"https://public.tableau.com/"};                  
        addParams(vizElement, paramsObj);
       var paramsObj = {"name":"embed_code_version", "value":"3" };  
         addParams(vizElement, paramsObj);                
         var paramsObj = {"name":"site_root", "value":"" };  
         addParams(vizElement, paramsObj);                
         var paramsObj = {"name":"name", "value":this.graphName };  
         addParams(vizElement, paramsObj);                
         var paramsObj = {"name":"tabs", "value":"no" };  
         addParams(vizElement, paramsObj);                
         var paramsObj = {"name":"static_image", "value":this.graphImage };  
         addParams(vizElement, paramsObj);                
         var paramsObj = {"name":"animate_transition", "value":"yes" };  
         addParams(vizElement, paramsObj);                
         var paramsObj = {"name":"display_static_image", "value":"yes" };  
         addParams(vizElement, paramsObj);                
         var paramsObj = {"name":"display_spinner", "value":"yes" };  
         addParams(vizElement, paramsObj);                
         var paramsObj = {"name":"display_overlay", "value":"yes" };  
         addParams(vizElement, paramsObj);                
         var paramsObj = {"name":"display_count", "value":"yes" };  
         addParams(vizElement, paramsObj);                
         var paramsObj = {"name":"language", "value":"en" };  
         addParams(vizElement, paramsObj);                
         var paramsObj = {"name":"filter", "value":"publish=yes" };  
         addParams(vizElement, paramsObj);  
         divElement.style="display: block;height:500px;width: 1250px;";         
       var scriptElement = document.createElement('script'); 
                        scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js'; 
                                           vizElement.parentNode.insertBefore(scriptElement, vizElement); 
      
    }
  },
    updated() {
        console.log("mounted tableau: " + window.location.pathname);
        this.toggle();
    }
}
</script>