express.java
=====
>A tiny RESTful web framework with embed server. Used as instead of JMX for cross-language communication.

## Features:

* ### Convention over Configuration
	
	No xml and no annotation. Just write an application by API in Java.
	
```java
	WebServer.jettyServer().get("/", new AjaxController() {
		@Override
		public Object ajax(ParamMap params) {
			return ResultMap.create().put("code", 200).put("msg", "ok");
		}
	}).get("/echo", new AjaxController() {
		@Override
		public Object ajax(ParamMap params) {
			return params;
		}
	}).get("/echo/${id}", new AjaxController() {
        @Override
        public Object ajax(ParamMap params) {
            return ResultMap.create().put("id", params.getInt("id"));
        }
    }).port(8080).start();
```
