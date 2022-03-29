# Development vs production

Next optimizes depending on the context (eg. TypeScript, fast refres and eslint for development) Each has different goals thus, different priorities.

Application code must be compiled, bundled, minified and code-split. Next handles these with its own compiler (written in Rust)

# Code splitting

Suppose your application has multiple pages (eg. urls) from which an user can _enter_. By code splitting you can split your bundle into several chunks so that only those that are required by each entry point are requested. Reducing loading time and network trafic.

In Next, each file in the `pages/` folder will be code-split into its own js bundle.

Also, code shared between pages is bundled together. Next can also pre-load code for other pages that the user is likely to visit afterwards.

# Three types of rendering

Rendering is the process of turning React code into its actual HTML representation. Next has three kinds of rendering you need to be aware of.

# Client-side rendering

If the HTML is not pre-rendered it must be done on the client side. But this will incurr in a delay between when the data is received by the client and when the client finishes rendering.

# Pre-rendering

Next pre-renders everything by default. There are two types of pre-rendering to be aware of

# Server-side Rendering

After _each_ request, the server will render and serve the resulting HTML. The server will then also send the required javascript to make the page interactive. In a process called _hydration_

# Static site generation

In contrast, in this, the HTML is rendered _once_. And delivered to a CDN. A client will receive the _static_ HTML from the CDN after the request.

In Next you can choose which rendering method fits your use case best. On a page-by-page basis

# From where are your apps distributed?

In Next, you can opt to distribute your app by several kinds of networks.

# origin servers

The main computer that sends stuff. Either directly to the client or the other network from which clients receive the content. The orign server must perform some computation when it receives a request. The result will be sent.

# Content Delivery Network

These are networks of computers around the world that server static content. When a client makes a request, the closest CDN will respond with the cached content. This has two main benefits. First, reduces the load on the origin server as it doesn't need to perform computations per each request. And it makes the page load faster for the user because it only receives the necessary static files from the closes location. CDNs are well suited for static pre-rendered pages.

# The Edge

This is just a concept that expresses the "fringe" of the network that is closest to any particular user. CDNs may be part of the Edge. But the Edge can run code as well. So you can take the caching approach of CDNs to "server-side" execution with Edge networks.

Therefore, you can move some of the work that used to be done either on the client or on the server into the Edge. This also has the purpose of making the application more performant. Reducing the amount of code that the client needs to process, on one hand, and reducing latency to the orign server on the other.

Next uses _middleware_ to run code in the Edge.
