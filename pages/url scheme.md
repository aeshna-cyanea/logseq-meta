- TODO [the official documentation]( https://docs.logseq.com/#/page/67520a99-da6d-42e6-b294-9740a4d08c97) is kinda unintuitive
  :LOGBOOK:
  CLOCK: [2024-12-20 Fri 10:41:46]--[2024-12-20 Fri 10:41:47] =>  00:00:01
  :END:
	- explanation of bookmarklet code courtesy of huggingchat/Qwen/QwQ-32B-Preview
		- ```js
		  // Variable declarations for document, window, base URL, location, encodeURIComponent, and parameter string
		  var d = document; // Document object
		  var w = window;   // Window object
		  var f = 'logseq://x-callback-url/quickCapture'; // Base URL for the custom scheme
		  var l = d.location; // Location object
		  var e = encodeURIComponent; // Function to encode URI components
		  var p = '?url=%27 + e(l.href) + %27&title=%27 + e(d.title) + %27&content=%27 + (w.getSelection? w.getSelection().toString() : d.getSelection? d.getSelection() : d.selection.createRange().text) + %27&x-source=bm%27'; // Parameter string with encoded URL, title, and selected text
		  - // Function to set location.href to the combined URL and parameters
		  function a() {
		    // Set location.href to the combined URL and parameters
		    l.href = f + p;
		  }
		  - // Check if the user agent contains "Firefox"
		  if (/Firefox/.test(navigator.userAgent)) {
		    // Use setTimeout with 0ms delay for Firefox
		    setTimeout(a, 0);
		  } else {
		    // Call the function directly for other browsers
		    a();
		  }
		  - // Use void(0) to prevent any default action
		  void(0);
		  ```
	- what do the settings in config.edn do exactly?
		- TODO `{url}`: URL or assets path for media files stored in Logseq.
			- what does this mean exactly? source or dest?
			- ```edn
			  :quick-capture-templates
			  {:text "[[quick capture]] **{time}**: {text} from {url}"
			   :media "[[quick capture]] **{time}**: {url}"}
			  
			  :quick-capture-options
			  {:insert-today? false
			   :redirect-page? true
			   :default-page "My Captured Page"}
			  ```