##  What is Node.JS?

> Node.js is an open source, cross-platform runtime environment for server-side and networking applications. Node.js applications are written in JavaScript, and can be run within the Node.js runtime on OS X, Microsoft Windows, Linux, FreeBSD, NonStop and IBM i.

note:
    ## What is the node runtime environment?

    Node runs on something called "V8" which is a javascript engine developed by Google. They developed this to use inside Google Chrome and it has been adopted by the creators of node to interpret and run javascript outside of the traditional browser context.

    V8 compiles javascript to native machine code before executing it, this is known as Just In Time compilation as the code is only compiled when it is required to be run. It also performs additional optimisations to your code dynamically based on heuristics of the codes execution profile. Things like inlining code if it is appropriate to do so among other things. [Info](http://jayconrod.com/posts/54/a-tour-of-v8-crankshaft-the-optimizing-compiler)
