1. When a user enters an URL in the browser, how does the browser fetch the desiredresult ?

Let's suppose we are hitting google.com in browser then following steps would occur: -

- The browser checks the cache for a DNS record to find the corresponding IP address of google.com.
- If the requested URL is not in the cache, ISP’s DNS server initiates a DNS query to find the IP address of the server that hosts google.com
- The browser initiates a TCP connection with the server.
- The browser sends an HTTP request to the webserver.
- The server handles the request and sends back a response.
- The server sends out an HTTP response.
- The browser displays the content.

Now let's talk about browser , it's components and how it displays content

    ![Alt text](../1.1/images/Browser-diagram.png?raw=true "Browser High Level Diagram")
    Main components of the browser
    - The User Interface: The user interface is the space where User interacts with the browser. It includes the address bar, back and next buttons, home button,      refresh and stop, bookmark option, etc. Every other part, except the window where requested web page is displayed, comes under it.
    - The Browser Engine: The browser engine works as a bridge between the User interface and the rendering engine. According to the inputs from various user  interfaces, it queries and manipulates the rendering engine.
    - The Rendering Engine: The rendering engine, as the name suggests is responsible for rendering the requested web page on the browser screen. The rendering engine interprets the HTML, XML documents and images that are formatted using CSS and generates the layout that is displayed in the User Interface. However, using plugins or extensions, it can display other types data also. Different browsers user different rendering engines:
    * Internet Explorer: Trident
    * Firefox & other Mozilla browsers: Gecko
    * Chrome & Opera 15+: Blink
    * Chrome (iPhone) & Safari: Webkit
    - Networking: Component of the browser which retrieves the URLs using the common internet protocols of HTTP or FTP. The networking component handles all aspects of Internet communication and security. The network component may implement a cache of retrieved documents in order to reduce network traffic.
    - JavaScript Interpreter: It is the component of the browser which interprets and executes the javascript code embedded in a website. The interpreted results are sent to the rendering engine for display. If the script is external then first the resource is fetched from the network. Parser keeps on hold until the script is executed.
    - UI Backend: UI backend is used for drawing basic widgets like combo boxes and windows. This backend exposes a generic interface that is not platform specific. It underneath uses operating system user interface methods.
    - Data Persistence/Storage: This is a persistence layer. Browsers support storage mechanisms such as localStorage, IndexedDB, WebSQL and FileSystem. It is a small database created on the local drive of the computer where the browser is installed. It manages user data such as cache, cookies, bookmarks and preferences.



Let's talk more about the rendering engine

    It’s able to render the content of given URL in browser screen and interprets the HTML, XML and CSS. It is single threaded. By default, It displays data according to your specified content type (MIME). For Example HTML, Images, XML, CSS, JSON, PDF etc.

    Key operation of Rendering engine is HTML Parser. Each browser use various engines like Chrome and Opera uses Blink, Firefox uses Gecko, IE Edge uses EdgeHTML, Internet Explorer uses Trident, Apple Safari uses WebKit.

    What is the Flow?
    1. Parsing HTML document by HTML Parser convert elements to Node and create Content Tree.
    2. Parsing Styles code / document by CSS Parser and create Render Tree.
    3. Render Tree goes through Layout Process. Element’s Node get position coordinates.
    4. Render Tree will be traversed and each node will be painted using the UI Back-end Layer.

    What does parsing means ?
     Parsing a document means translating it to a structure the code can use. The result of parsing is usually a tree of nodes that represent the structure of the document. This is called a parse tree or a syntax tree.



