<h1> Two Common Topics for TypeScript Interviews </h1>
<p>In this article, we are going to shed light on two common TypeScript interview topics.</p>

The topics are:
<ol>
<li><a href="#type-vs-interface">Differences Between Types and Interfaces</a></li>
<li><a href="#type-inference">Type Inference and Its Advantages</a></li>
</ol>
<hr/>


<div id="type-vs-interface">
<h2>Differences Between Types and Interfaces</h2>

<p>Let's start with the basics. Why do we need 'Types' and 'Interfaces'?</p>

<p>In every programming language, we have primitive data types. As useful as they are, they are not enough. Eventually, we need collections and compound data types.</p>

<p>In Object-Oriented Programming, we use classes to define compound data types — specifically, to define the shape of objects. TypeScript offers two additional ways to achieve the same goal: type aliases and the interface construct.</p>

<p>Let's assume we want to work with some user objects. We can define the shape of these objects using either a type alias or the interface construct.</p>

<pre>
```ts

type User = {
  id: number;
  name: string;
  email: string;
};

```
</pre>
</div>

<hr/>


<div id="type-inference">
<h2>Type Inference and Its Advantages</h2>
</div>

