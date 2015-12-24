# summary #

The filter wraps any response content into a js string (except json type responses, they will be left as they were), and send it back to client as a jsonp callback.

Function name of the callback depends on a customizable request parameter; and a request without the parameter will simply jump over the filter.


# configuration #
**parameter defaults**
| **param-name** | **default-value** | **description** |
|:---------------|:------------------|:----------------|
| **jsonp**      | callback          | name of the request parameter contains callback function name. |
| **json-mime-types** | application/json, application/x-json, text/json, text/x-json | mime-types of json responses that won't be wrapped as plain text. |


# example #
**web.xml**
```
 <filter>
   <display-name>jsonp</display-name>
   <filter-name>jsonp</filter-name>
   <filter-class>org.jsonp.JsonpFilter</filter-class>
   <init-param>
     <param-name>jsonp</param-name>
     <param-value>jsonpCallback</param-value>
   </init-param>
   <init-param>
     <param-name>json-mime-types</param-name>
     <param-value>application/json</param-value>
   </init-param>
 </filter>

 <filter-mapping>
   <filter-name>jsonp</filter-name>
   <url-pattern>*</url-pattern>
 </filter-mapping>

 <mime-mapping>
   <extension>json</extension>
   <mime-type>application/json</mime-type>
 </mime-mapping>
```

checkout http://jsonp-java.googlecode.com/svn/trunk/src/test/webapp/ for a demo app