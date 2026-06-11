Piecing Together a Proof

I’ve spent most of my time as a TA this quarter trying (with limited success) to convey to mt Math 115A students the way I think about writing proofs. Finally, in my office hour last Tuesday, I landed on something that seemed to work. For posterity, and for any students this quarter who weren’t at that office hour making a last-minute push before Friday’s final, I wanted to write up this explanation.

This explanation first came to me by analogy with jigsaw puzzles. As children, we all arrive at more or less the same strategy for solving these puzzles: you first identify the corner pieces, whose placement in the puzzle is known more or less a priori; then you try to fit together the edges, which require a bit more work to identify, but connect in obvious ways to each other and to the corners; finally, with the frame constructed, you work your way inwards, occasionally assembling floating clusters of pieces whose context is not known yet, until you have assembled the entire picture. 

Mathematicians employ a similar approach in writing proofs (or at least the short ones encountered in an undergraduate course). Each proof starts and ends with some “frame pieces,” which almost always look roughly the same regardless of what needs to be shown, and once this “frame” is in place, it often hints at how the middle of the proof should go. The difficulty of a problem essentially comes down to how hard it is to fill in the middle. 

Let me give an example of what I mean before speaking in any more generality:

**Proposition:** Let $S$ and $T$ be subsets of a vector space $V$. Show that if $S \subseteq T$, then $Span(S) \subseteq Span(T)$$. 

If you’re taking Math 115A right now, you should spend a few minutes thinking about how to prove this before reading ahead. If you think you know, write up your proof (in full).

Thought about it? Good. Now, let’s discuss.

The first thing you should do when writing a proof is write down the first and last line. Once you’ve done it enough, you’ll realize that this step doesn’t require any specialized knowledge, just the ability to parse the problem statement. The first line should introduce the main objects you’ll be working with, including their main properties; the last line should be a restatement of the conclusion of the problem. In this case:


*Proof:* **Let $S$ and $T$ be subsets of $V$ such that $S \subseteq T$**

…

**Thus, $Span(S) \subseteq Span(T)$** 


Next, we need to write the second and second-to-last lines. These should just be explanations of the first and second lines; the second line should clarify the facts made available by the first line; and the second-last line should be a statement which, once shown, implies the last line. In this case, a natural thing to do is to unpack the “$\subseteq$” relation—this may seem too clear to need unpacking, but you should do it anyway!

*Proof:* Let $S$ and $T$ be subsets of $V$ such that $S \subseteq T$.

**So, if $s \in S$, then $s \in T$.**

…

**So, for all $v \in Span(S)$, we have $v \in Span(T)$.**

Thus, $Span(S) \subseteq Span(T)$. 

We can keep working our way inwards. Typically, the third line of the proof will introduce the variable or variables which, so far, appear only in the second-to-last line. In this case, the penultimate line is a statement about all $v \in Span(S)$; the third line needs to introduce the variable $v$ representing an element of $Span(S)$. There is no general formula for the third-to-last line, but often, as in this case, it will be a further unpacking of the second-to-last line:

 *Proof:* Let $S$ and $T$ be subsets of $V$ such that $S \subseteq T$.

So, if $s \in S$, then $s \in T$.

**Let $v \in Span(S)$.**

…

**So, if $v$ can be written as a linear combination of elements in $S$, then it can be written as a linear combination of elements in $T$.**

So, for all $v \in Span(S)$, we have $v \in Span(T)$.

Thus, $Span(S) \subseteq Span(T)$. 


As long as there are definitions to unpack, you can keep writing the proof more-or-less on autopilot. In this case, the fourth line follows immediately from the third.

*Proof:* Let $S$ and $T$ be subsets of $V$ such that $S \subseteq T$.

So, if $s \in S$, then $s \in T$.

Let $v \in Span(S)$.

**Then $v$ can be written as a linear combination of elements in $S$, i.e. as $\sum_{s_i \in S} a_i s_i$, where the $a_i$’s are elements from the ground field.**

…


So, if $v$ can be written as a linear combination of elements in $S$, then it can be written as a linear combination of elements in $T$.

So, for all $v \in Span(S)$, we have $v \in Span(T)$.

Thus, $Span(S) \subseteq Span(T)$. 


By now, it is hopefully clear how to fill in the proof. (If not, take a couple minutes to think before seeing how I do it!).

I would write:

*Proof:* Let $S$ and $T$ be subsets of $V$ such that $S \subseteq T$.

So, if $s \in S$, then $s \in T$.

Let $v \in Span(S)$.

Then $v$ can be written as a linear combination of elements in $S$, i.e. as $\sum_{s_i \in S} a_i s_i$, where the $a_i$’s are elements from the ground.

Since each $s_i \in S$ and $S \subseteq T$, we know that each $s_i \in T$. Thus, $v = \sum_{s_i \in S} a_i s_i$ is in fact a linear combination of elements in $T$. 

So, if $v$ can be written as a linear combination of elements in $S$, then it can be written as a linear combination of elements in $T$.

So, for all $v \in Span(S)$, we have $v \in Span(T)$.

Thus, $Span(S) \subseteq Span(T)$. 

Once you’ve written the entire proof like this, you can revise it if you’d like - this “outside-in” approach doesn’t produce the most eloquent arguments - but this is probably the best way to begin the proof-writing process.

Before getting into any more examples, let me make a few general remarks:

The first and last lines of the proof require no subject-matter knowledge whatsoever. I could walk into the final exam for a graduate-level course I’ve never taken, and while I wouldn’t be able to solve any of the problems, I could certainly come up with the first and last lines of every proof. 
The second and second-last lines require subject-matter knowledge but no mathematical insight. They are usually just definitions of terms appearing in the first and last lines. If you can’t figure out what to write here, it probably means you don’t know the definition well-enough! You should keep unpacking definitions until there’s nothing left to unpack. Sometimes you’ll find you’ve unpacked too far, in which case you can cross out whatever you don’t wind up using. The deeper you get into a proof, the more you’ll need to rely on insights, tricks, calculations, etc. 
Your proofs should be symmetric. Each variable appearing at the end of the proof should be introduced at the beginning (and its first appearance should be roughly as close to the start of the proof as its final appearance is from the end). You should **always define a variable before using it in your proof! (Even if it appears in the problem statement)!** For this reason, it’s often helpful to write the last line first; the first line is just an introduction of the variables appearing in the last line (including their basic properties). In this spirit of setup and payoff, you also shouldn’t introduce a variable until you’ve figured out how it will ultimately be used. 

Here are some basic bits of parallelism and phraseology you should be aware of:

A line at the end of the proof of the form “Thus, all _ have property P” should be paired with a line at the start of the proof of the form “Let x be a _.” In the sample proof, for instance, the second-to-last line read: “so, for all $v \in Span(S)$, we have $v \in Span(T)$.” To match this, we wrote as the third line: “Let $v \in Span(S)$.” 
If you are trying to prove a statement of the form “If an object has property P, then it has property Q,” the first line will usually be “suppose x has property P” and the last line should be “then x has property Q.”
When you need to prove an inclusion of subsets, e.g that $S \subseteq T$, what you are really trying to prove is that “if $x \in S$, then $x \in T$.” 
When you want to prove that two sets are equal, i.e. $S = T$, what you are really proving is that $S \subseteq T$ and $T \subseteq S$. Likewise, if you want to prove that two *numbers* are equal, i.e. $n = m$, it is sometimes easier to prove that $n \leq m$ and $m \leq n$. 
Proving a statement of the form “there exists y with property P is usually a bit trickier.” Often, the corresponding line at the start of the proof should be an exact description of that object y, but this is often hard to see right away. Typically, you need to play around with the information at the start of the proof for a while to see how the construction of y should go. On the other hand, it is not uncommon to prove the existence of an object using some theorem or definition. In this case, you might be able to establish the existence of $y$ without ever saying what it is. (For instance, if you know a given set is linearly dependent, then you are guaranteed the existence of certain linear combinations, even if you can’t give an explicit description of them).
By contrast, if part of the given information is that “there exists y with property P,” then one of the first lines of the proof should be “Let y have property P.” 

Let’s demonstrate this with a couple of examples. 

**Exercise:** Let $A, B, C$ be sets; let $f: A \to B$ and $g: B \to C$ be injective functions. Show that $g \circ f$ is injective.

As before, the first and last lines can be extracted directly from the problem statement:


*Proof*: **Let $A, B, C$ be sets and $f: A \to B$, $g: B \to C$ injective functions.**

…

**Thus, $g \circ f$** is injective. $\qedsymbol$** 


The second and penultimate lines are explanations of the first and last lines


*Proof*: Let $A, B, C$ be sets and $f: A \to B$, $g: B \to C$ injective functions.

**Then if $a, a’ \in A$ satisfy $f(a) = f(a’)$, $a = a’$; likewise, if $b, b’ \in B$ satisfy $g(b) = g(b’)$, then $b = b’$.**

…

**So, if $x, x’ \in A$ satisfy $(g \circ f)(x) = (g \circ f)(x’)$, $x =x’$.**

Thus, $g \circ f$** is injective.


You’ll notice that I’ve used the names $a, a’ \in A$ to describe the property of $f$ being injective, and the names $x, x’ \in A$ to describe the property of $(g \circ f)$ being injective. This is not strictly necessary, but since these variables exist for different purposes, giving them different names might help to avoid confusion. 

Now, since i’ve introduced $x$ and $x’$ at the end of the proof, we need to formally define them at the start of the proof. We should also make a note of what exactly needs to be shown about $x$ and $x’$ once they have been introduced:

*Proof*: Let $A, B, C$ be sets and $f: A \to B$, $g: B \to C$ injective functions.

Then if $a, a’ \in A$ satisfy $f(a) = f(a’)$, $a = a’$; likewise, if $b, b’ \in B$ satisfy $g(b) = g(b’)$, then $b = b’$.

**Now, fix $x, x’ \in A$, and suppose that $(g \circ f)(x) = (g \circ f)(x’)$.**

…

**Then $x = x’$.**

So, if $x, x’ \in A$ satisfy $(g \circ f)(x) = (g \circ f)(x’)$, $x = x’$.

Thus, $g \circ f$** is injective.


That second line could use a bit of explanation; specifically, we should unpack how the function $g \circ f$ is defined: 


*Proof*: Let $A, B, C$ be sets and $f: A \to B$, $g: B \to C$ injective functions.

Then if $a, a’ \in A$ satisfy $f(a) = f(a’)$, $a = a’$; likewise, if $b, b’ \in B$ satisfy $g(b) = g(b’)$, then $b = b’$.

Now, fix $x, x’ \in A$, and suppose that $(g \circ f)(x) = (g \circ f)(x’)$.

**That is, g(f(x)) = g(f(x’))**

…

Then $x = x’$.

So, if $x, x’ \in A$ satisfy $(g \circ f)(x) = (g \circ f)(x’)$, $x = x’$.

Thus, $g \circ f$** is injective.


At this point, we have completed the frame of the proof; now, we just need to fill in the rest, by using what we know about the functions and variables in play. Take a moment to try this for yourself, then have a look below at how I’ve done it:

*Proof*: Let $A, B, C$ be sets and $f: A \to B$, $g: B \to C$ injective functions.

Then if $a, a’ \in A$ satisfy $f(a) = f(a’)$, $a = a’$; likewise, if $b, b’ \in B$ satisfy $g(b) = g(b’)$, then $b = b’$.

Now, fix $x, x’ \in A$, and suppose that $(g \circ f)(x) = (g \circ f)(x’)$.

That is, g(f(x)) = g(f(x’))

**Since $g$ is injective, we must have $f(x) = f(x’)$**

**Since $f$ is injective, it follows that $x = x’$**

Then $x = x’$.

So, if $x, x’ \in A$ satisfy $(g \circ f)(x) = (g \circ f)(x’)$, $x = x’$.

Thus, $g \circ f$** is injective. $\qedsymbol$. 

Having completed the proof, we might want to clean it up a bit. For example, in retrospect, we didn’t really need to unpack the definition of injectivity at the start. You might revise it to look more like the following:

*Proof:* Let $A, B, C$ be sets, and let $f: A \to B$ and $g: B \to C$ be injective functions. Suppose we have $x, x’ \in A$ such that $(g \circ f)(x) = (g \circ f)(x’)$, that is, $g(f(x) = g(f(x’))$. Since $g$ is injective, this implies $f(x) = f(x’)$; since $f$ is injective, it follows that $x = x’$. Thus, if $(g \circ f)(x) = (g \circ f)(x’)$, $x = x’$ - in other words, $g \circ f$ is injective. $\qedsymbol$. 

Even though we wound up deleting the line explaining what it meant for $f$ and $g$ to be injective, it was still worth including in a first draft - we didn’t know it wouldn’t be important until we had written the rest of the proof! Writing this line is also a good way to remind yourself of the relevant definitions—and to check if you actually know them! We wound up using the fact that f and g were injective in our proof, for instance, just not with the variables $a, a’, b, b’$. 


Here’s a similar exercise that illustrates how to deal with “there exists” quantifiers. You should really try to do this one yourself first, following the model of the last exercise!


**Exercise:** Let $A, B, C$ be sets and $f: A \to B$, $g: B \to C$ functions. Show that if $f$ and $g$ are surjective, then so is $g \circ f$. 


As usual, we start with the beginning and end:


*Proof:* **Let $A, B, C$ be sets and let $f: A \to B$ and $g: B \to C$ be surjective functions.**

…

**Thus, $g \circ f$ is surjective.**


Now, we unpack the first and last lines:


*Proof:* Let $A, B, C$ be sets and let $f: A \to B$ and $g: B \to C$ be surjective functions.

**Then for any $b \in B$, there exists $a \in A$ such that $f(a) = b$; likewise, for any $c’ \in C$, there exists $b’ \in B$ such that $g(b’) = c’$.**

…

**So, for any $z \in C$, there exists $x \in A$ such that $(g \circ f)(z) = x$.**

Thus, $g \circ f$ is surjective.


Again, I’ve made some slightly unusual choices about variable names in order to avoid using the name same for different variables. (In particular, $b$ and $b’$ serve different roles, so I wanted to call them different things, even though technically it would be fine to use the same symbol for both).

Now, since we have mentioned $z$ at the end of the proof, we need to introduce it at the start. Also, as before, we should unpack the notation $(g \circ f)$: 

*Proof:* Let $A, B, C$ be sets and let $f: A \to B$ and $g: B \to C$ be surjective functions.

Then for any $b \in B$, there exists $a \in A$ such that $f(a) = b$; likewise, for any $c’ \in C$, there exists $b’ \in B$ such that $g(b’) = c’$.

**Now, consider an element $z \in C$.**

…

**So, there exists $x \in A$ such that $g(f(x)) = z$.**

So, for any $z \in C$, there exists $x \in A$ such that $(g \circ f)(z) = x$.

Thus, $g \circ f$ is surjective.


Now that there is nothing left to explain, it is time to fill in the proof. 

*Proof:* Let $A, B, C$ be sets and let $f: A \to B$ and $g: B \to C$ be surjective functions.

Then for any $b \in B$, there exists $a \in A$ such that $f(a) = b$; likewise, for any $c’ \in C$, there exists $b’ \in B$ such that $g(b’) = c’$.

Now, consider an element $z \in C$.

**Since $g$ is surjective, there exists $y \in B$ such that $g(y) = z$.**

**Since $f$ is surjective, there exists $x \in A$ such that $f(x) = y$.**

**Hence, $g(f(x)) = g(y) = z$.**

So, there exists $x \in A$ such that $g(f(x)) = z$.

So, for any $z \in C$, there exists $x \in A$ such that $(g \circ f)(z) = x$.

Thus, $g \circ f$ is surjective. $\qedsymbol$. 


Before finishing off this post, let me make a quick remark about “indirect” proofs. If you are attempting a “proof by contrapositive”—that is, trying to show “if P, then Q” by proving “if not Q, then not P,” then the process of proof-writing goes more-or-less as above, with the problem statement replaced by its contrapositive. So, you’ll start (in the first line) by introducing variables representing objects satisfying “not Q,” and wind up, in the last line, showing that these objects must satisfy “not P.” Negating P and Q properly can be a bit delicate, especially for beginners, but that’s a story for another time. 

On the other hand, a proof by contradiction is much harder to come up with “outside-in.” You'll always start by assuming “P and not Q,” but the last line will be some contradiction (which is generally hard to guess before finding it). I think most of the proofs by contradiction I’ve written have started off as proofs by contraposition, and became proofs by contradiction by accident after playing around for a while. 


I’ll leave you with an exercise to try on your own:

**Exercise:** Let $A$ and $B$ be sets and $f: A \to B$ a function. Show that if $f$ has a left-inverse, then it is injective. Similarly, show that if $f$ has a right-inverse, then it is surjective. 









