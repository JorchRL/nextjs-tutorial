# Using Next

We will have to use npm

`npm install react react-dom next`

# Pages

As Next is a _framework_ some lower-level details that you still have to do in plain React will be done for you on Next.

Make a folder named pages and add a React component in a jsx file. Then run `next dev`.
Thats it. You created a page. It also automagically _fast refreshes_

# Libraries vs Frameworks

Here is a useful heuristic. React is a libraty that provides essential primitives that you may call. But Next is a framework. It does a lot of stuff you would need to do yourself if you used just React. A framework _calls your functions_ while with libraries _you call their functions_. So frameworks provide the extra scaffolding that you would need to build yourself should you choose to use just the library.
