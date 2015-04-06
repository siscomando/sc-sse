sc-sse
============

sc-sse is webcomponent to Server Side Events of HTML5

Usage
=====

```
<body unresolved>
		<span>See console messages</span>
		
        <sc-sse stream="http://localhost:8080/stream" channel="userlogon" alias="updates"></sc-sse>

        <script>
        	var sse = document.querySelector('sc-sse');
        	sse.addEventListener('sc-sse-response', function(e) {
        		// channel is useful when to receives from one URL stream 
        		// that returns differents data as users, comments or issues 
        		// updates where theses are implemented in server side.
        		console.log("Reply from channel[" + channel "]: " + e.detail.response);
        		// alias is useful when multiple sc-sse in same page.
                        // alias it's a name for the data returned by sc-sse 
                        // custom element.
                        if (e.detail.alias == "updates") {
                                console.log("Returned data from updates sc-sse");        
                        }
        		
        	});
        </script>

</body>
```



