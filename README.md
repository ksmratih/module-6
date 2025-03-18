## Reflection 1

The handle_connection function is responsible for processing incoming TCP connections from a web client. It takes a mutable TcpStream as input, wraps it in a buffered reader to enable efficient line-by-line reading, and reduces system calls. The function reads the HTTP request by iterating through each line of the input stream, mapping the results to handle errors, and stopping at the first empty line, which marks the end of the request headers. Finally, it collects the request lines into a vector and prints them in a formatted output to the console for debugging.

## Reflection 2

![Commit 2 screen capture](assets/images/commit2.png)

We modified the handle_connection function to return an HTML response that can be rendered by a browser. Instead of just printing the HTTP request, the function now reads an hello.html file and constructs a proper HTTP response, including a status line (HTTP/1.1 200 OK) and a Content-Length header to indicate the size of the response body. This ensures the browser can correctly interpret and display the content. The response is then written to the TCP stream, allowing the browser to render the HTML page. This step helped in understanding how a basic web server serves static files and the importance of properly formatting HTTP responses.

## Reflection 3

