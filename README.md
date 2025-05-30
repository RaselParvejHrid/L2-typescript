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

<p>In Object-Oriented Programming, we use classes to define compound data types — specifically, to define the shape of objects. TypeScript offers two additional ways to achieve the same goal: the <b>type</b> aliases and the <b>interface</b> construct.</p>

<p>Let's assume we want to work with some <b>User</b> objects. We can define the shape of these objects using either a <b>type</b> alias or the <b>interface</b> construct.</p>

Using <b>type</b> alias,
```ts
type User = {
  id: number;
  name: string;
  email: string;
};
```


Or, using <b>interface</b> construct,
```ts
interface User {
  id: number;
  name: string;
  email: string; 
}
```

<p>Regardless how we model the <b>User</b> data type, we can now use this data type as the data type of variables and assign, to these variables, values that matches the declaration of the <b>type</b> alias, or the <b>interface</b> construct.</p>

```ts
let user: User = {
    id: 1,
    name: "Siyam",
    email: "samba@gmail.com"
};
```


<h3>Are they exactly the same thing then?</h3>
<p>Though they share goals and can replace one another often, they also have some important differences.</p>

<ol>
<li>
On Re-declaration with same identifier, interfaces just merge.

```ts
interface A { x: number; }
interface A { y: string; }  // Merges with the first 'A'
```
On the other side, Redeclaration with same identifier is a syntax error for <b>type</b> alias.

```ts
type A = { x: number; };
// type A = { y: string }; ❌ Error: Duplicate identifier 'A'
```
</li>

<li>
<b>interface</b> are to define the shape of objects.<br/>
But, a <b>type</b> can work as an alias for any data type including primitive types.

```ts
type ID = number; // Alias for a Primitive Type
```
</li>

<li>
<b>interface</b>s are extensible, as in OOP Inheritance. <br/>
We can combine more than one types into a single type, using operators like <b>|</b> and <b>&</b>; but this cannot be called 'Extending' in terms of OOP Inheritance. It's more like creating a new type from two or more types, rather than inheriting and extending a type.

```ts
interface Person {
  name: string;
  age: number
}

// Interface extension
interface Employee extends Person {
  role: string;
}

type BaseType = { id: number };
type UserType = BaseType & { name: string; }
/*
It's more like creating a new type from two types,
namely, the type BaseType, and the unnamed type { name: string; }
*/
```
</li>


</ol>

I hope, this answers your question on 'Differences between Types and Interfaces on TypeScript'.
</div>

<hr/>


<div id="type-inference">
<h2>Type Inference and Its Advantages</h2>
<p>Now we will discuss 'What is Type Inference in TypeScript?', and the advantages of Type Inference, for us, the Developers.</p>


<p>Why do we JavaScript developers use TypeScript?</p>

<p>Because JavaScript—an amazing and powerful language—surprisingly lacks type safety. For small web scripts or tiny programs, this may seem like a blessing or not much of a concern. But as the codebase grows, we begin to feel the need for stronger structure and safety in data types. That’s exactly why we use TypeScript. Being a superset of JavaScript, it offers the best of both worlds: all of JavaScript, plus type safety.</p>

<p>Yes, TypeScript = JavaScript + Type Safety.</p>

<p>But that doesn’t mean we get type safety for free just by using TypeScript. We still have to put in some effort to achieve it. What kind of effort? We need to explicitly type our variables, functions, objects, and so on to enjoy the full benefits of type safety.</p>

<p>That said, the TypeScript compiler is quite intelligent. In many cases, we don’t need to do everything manually. Thanks to type inference, TypeScript can often figure out the types for us automatically.</p>

<p>Let's explore some examples.</p>

We can do as follows in TypeScript, while declaring a variable, thus achieving type safety on the following variables.

```ts
let name : string = "Alice"; // We explicitly specify: string
let age : number = 30;       // We explicitly specify: number
let isActive : boolean = true; // We explicitly specify: boolean
```


But, note that, we are not only declaring a variable and its type here, we are also assigning to it a value on the same statement.

<p>Type Inference is tied with assignment of a value while declaring it.</p>

Because, we are assigning a value to the variable in the same statement the variable is being declared in, thanks to <b>Type Inference</b> capability of TypeScript, we can omit specifying the type of the variable, as bellow.

```ts
let name = "Alice"; // TypeScript infers: string
let age = 30;       // TypeScript infers: number
let isActive = true; // TypeScript infers: boolean
```

<p>TypeScript infers the type of the variable from the assigned value in the same statement. If we intend the type of the variable to be exactly the type of the assigned value, we can accept Type Inference and omit explicitly specifying type.</p>

<p>Type Inference is not only associated with variable declaration. We can see it in  cases of Function Return Type, Array Type, Destructuring of Arrays and Objects etc. </p>

<p>So, we have explained what <b>Type Inference</b> is. Now, let's discuss its usefulness.</p>

<ol>
<li>
The obvious advantage is 'Less Code'. It reduces Verbosity of code, without compromising Type Safety, especially when the type is a long string of symbols and characters.
</li>

<li>
Code Verbosity costs time too. A developer may need much time to infer a type; but TypeScript is much faster than him/her. So, type inference improves developer's productivity, with no slightest loss of type safety.
</li>

<li>
This developer productivity is present not only while writing the code for the first time, but also while refactoring it. Thanks to Type Inference, the responsibility of re-inferring types is on TypeScript, not on the developer.
</li>

</ol>

So, we should always be aware of Type Inference; and take advantage of it every single time it is offered.


</div>

