##  Why would you not use Node.JS?

-------------

- It's Javascript! (No compile time checking for errors) <!-- .element: class="fragment" data-fragment-index="1" -->
- It doesn't handle running things that will block execution (like computations, or complex logic) very well <!-- .element: class="fragment" data-fragment-index="2" -->
- It requires more developer discipline than other languages <!-- .element: class="fragment" data-fragment-index="3" -->
- You can get into callback hell if you aren't careful <!-- .element: class="fragment" data-fragment-index="4" -->

        asyncFunction1(function(err, result) {
            // Do some stuff
            asyncFunction2(function(err, result) {
                // Do some more stuff
                asyncFunction3(function(err, result) {
                    // Probably code here too
                    asyncFunction4(function(err, result) {
                        // Yep, still going
                        asyncFunction5(function(err, result) {
                            // FINALLY
                        });
                    });
                });
            });
        });
<!-- .element: class="fragment" data-fragment-index="4" -->

note:

    You can remedy this slightly with static analysis tools such as Linters / FlowType from facebook

    Bitcoin miners are a no go! This is because node is inherently single threaded by nature and can only process one path of execution at a time.

    Because you don't have the traditional constructs such as Classes / Interfaces / Namespaces it becomes important to really understand your architecture very well and to understand the various methods that can be used to mimic these constructs in JS.
