# summary #

The filter wraps any response content into a js string (except json type responses, they will be left as they were), and send it back to client as a jsonp callback.

Function name of the callback depends on a customizable request parameter; and a request without the parameter will simply jump over the filter.


[UserGuide](UserGuide.md)