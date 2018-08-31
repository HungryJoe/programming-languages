## Lecture 1.3

(under construction)

##### Programming languages you were interested in

- Haskell
- Fortran/Algol (sth old), 
- Go, 
- PhP, 
- Julia, 
- Q#, 
- Matlab, 
- Ruby on Rails, 
- ... probably some more ... 

one language I would like to add is 

- Elm which implements [Functional Reactive Programming](https://en.wikipedia.org/wiki/Functional_reactive_programming), picking up on a discussion we had in class of how to reconcile the idea of functional programming with the idea of not having just one input and one output but rather streams of inputs and outputs and then continue potentially forever

there was also the question about using python for a machine learning project ... I think you need to be able to argue that your project contributes to learning sth new about Programming Languages ... so if you used machine learning to analyse the data on github in order to learn sth new about Programming Languages that could be possible ... so I add

- machine learning Programming Languages data

)

##### Summary of what we learned so far:

- computation as rewriting 
  - build terms from operations
  - rewrite terms by applying equations using pattern matching
  - equations are also called rewrite rules in this context
- computation terminates if no rule applies
  - a term to which no rule applies is called a **normal form**
  


(we talked about how it is important in research to simplify a problem in the right way; we learned some basic ideas: computation as rewriting to normal form; now let us make things more complicated again and see how far we can go ... there are many ways to do this: negative numbers, binary numbers (or decimals), exponentiation, square roots, calculus, if-then-else, etc etc ... but we will look at something else first, namely how to go from numbers to algebra, or from primary school to secondary school)

#### Algebra

How far did we go in our quick tour of school mathematics? Roughly primary school, computing with numbers. 

Algebra induces a radical new **big idea**: instead of thinking of variables as place holders for terms/numbers: variables as "first class citizens"

Historically, this did not come easy. The first time the method of algebra appears fully developed in most of its basic ideas is a turning point in history. Please have a look at [Descartes' Geometry](http://www.gutenberg.org/ebooks/26400), first published in 1637. (It is always worth looking at Wikipedia so read up on [Descartes](https://en.wikipedia.org/wiki/René_Descartes) who led a very interesting live that is full of amusing anecdotes and his books, the [Discourse on the Method](https://en.wikipedia.org/wiki/Discourse_on_the_Method) and its appendix, the [Geometry](https://en.wikipedia.org/wiki/La_Géométrie), are, in my opinion, arguably the most important publications in philosophy and mathematics of all time. A great resource on  philosophy and logic and some areas of mathematics is the Stanford Encyclopedia of Philosophy which also has an article on [Descartes mathematics](https://plato.stanford.edu/entries/descartes-mathematics/).) Even if you don't read French, just by browsing through the pages, you see that Descartes, who just escaped the middle ages, did write in a style that is still readable today and that looks like modern mathematics. You can also look at a [facsimile of the original](). Even without trying to understand the maths in detail, I found for example [page 301 of the original](https://fr.wikisource.org/wiki/Page:Descartes_La_Géométrie.djvu/11) worth looking at. We see that he didnt use "=" (which, in fact, was introduced already earlier by [Robert Recorde](https://en.wikipedia.org/wiki/Robert_Recorde) in 1557 but not widely used yet), but that otherwise all is already there. 

		Little research project: Why did Descartes use a symbol for "=" that is not symmetric? 
		Could there be a connection to the idea of rewriting that we mentioned above?
		
It can help to appreciate the importance of Descartes' contribution by putting him into the historical context. He was a generation younger then Galileo and a generation older than Newton. Looking at Galileo's [theorems of motion](http://galileoandeinstein.physics.virginia.edu/tns_draft/tns_153to160.html) as formulated by himself in the celebrated [Discourses and Mathematical Demonstrations Relating to Two New Sciences](https://en.wikipedia.org/wiki/Two_New_Sciences), we see that he needs 6 theorems with complicated proofs in order to express the simple equation d=v*t because he does not have the algebra of Descartes. (Thanks to Andrea DiSessa, Changing Minds (2002) for pointing this out.)
	
Ok, after this historic excursion, let us go back to calculating with terms containing variables.

		do we need new equations?
			what, for example, about (x+y)+x = 2x+y ? Get out pen and paper.
		needs commutativity
		write out all equations we have so far (could do this together at the whiteboard)
		innocent but important question: how do we know that we have all equations?

The answer to the last question, leads to the next topic, the title of which contains 4 **big ideas**.

But first, we could use this opportunity to get used to consult research literature. The problem we have been discussing has an interesting history and drew the attention of some real heavyweights. Read up to (and excluding) Section 1.1 of the [article by Burris and Yeats](https://www.math.uwaterloo.ca/~snburris/htdocs/MYWORKS/PREPRINTS/saga.ps). Can you summarise its contents? (I don't expect you to be able to do this now, we will explain everything in detail ... but if you try now, you will understand better what follows.)

Also read the Wikipedia article on [Tarski's High School Algebra Problem](https://en.wikipedia.org/wiki/Tarski%27s_high_school_algebra_problem).

#### Soundness, Completeness, Syntax, Semantics

##### Soundness and Completeness
		First review how we use equations for computations. Emphasise that this is as in high school.
		Two important questions arise:
		Soundness: How do we know that the equations are correct?
		Completeness: How do we know that we found all equations?
		How do we even start thinking about these questions? Brainstorm with the students ...
		Answer will be (at this moment only informal discussion):
			syntax vs semantics
			terms vs algebras
				computation syntactically as rewriting of terms
				computation semantically by evaluating terms in an algebra
				[rewriting of terms amounts to implementing an interpreter for a programming language
				 evaluating in an algebra takes the algebra as a device capable of computation as primitive]
			language vs models
			soundness: The equations are true in the intended model
			completeness: All equations that hold in the intended model can be derived using the equations
			what is the language in our example?
			what is the model in our example?
			can we keep them separated? this is difficult if this is a new idea to you, requires lots of practice
			let us try to make this very explicit by using different notation
			what does relate the two different realms of formal language and their models?
				there is a meaning function ... write it out ...
				explain how 
					the formal language is a programming language
					the meaning function is an interpreter
					the meaning function is compositional (or recursive (but maybe keep this for later))
					how can we make "compositional" more precise? (just mention this question for later)

### Summary of big ideas
 - terms are trees (maybe only a small idea? But it is of fundamental importance)
 - variables as first class citizens (ideas can seem small in hindsight, that is why I emphasised Descartes)
 - syntax (syntax has no meaning, just given by `naked' rules)
 - semantics (semantics is a map from syntax to "meaning" ... do you see the self-reference here?)
 - soundness (are the rules correct?)
 - completeness (do we have all rules?)
 
