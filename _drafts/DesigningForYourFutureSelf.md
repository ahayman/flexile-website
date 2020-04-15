##Designing for your future self 

Something like 80%[^1] of the the time we spend as software developers is time spent _maintaining_ our code.  Some people are going to read that first sentence, sigh and move on because it's not like people haven't talked about why you should write maintainable code: "Yeah, yeah, I need to Unit Test, I know...".  And _yet_, the vast majority of conversations I see between developers aren't about how to make your code more maintainable, but are instead about how to make your software _easier to write_, which is emphatically not the same thing.  In the iOS world (and I would generalize this out to the world of "Mobile Software Development") this is particularly a problem where the general market encourages "quick and dirty" development as the stakeholders[^2] have been focused on either ramping up quickly (read: catching up to competitors) or else trying out new ideas (venture software development) to see what works.  In this market, it literally _pays_ to be able to get new features and entire apps developed quickly and without regard to long term sustainability.  Unfortunately, it is precisely this reason that the maintainability of the code base basically goes to shit and as a project moves into the long term, development costs grow exponentially at the same time that new features grind to halt.  To put bluntly:

> Developing maintainable code is so far removed from developing MVP projects, that you might as well consider them two completely different things.

Yes, they're both software development and perhaps the end product might actually look the same (from a user's standpoint), but the underlying code base will be completely different and the skill set necessary to accomplish one vs the other is completely different.  

If you _are_ a stakeholder, and you're looking through what probably is a sea of qualified developers, take the time to note the difference and understand what you are buying.  Developers who write long-term maintainable code are _expensive_.  They're normally older, have more experience, and/or have studied specifically to develop maintainable software.  They will quote _longer_ time lines that cost you much more money upfront because they'll be quoting software that can grow and be maintained.  Contrasted with the vast majority of mobile developers out there, you'll probably scoff at the prices.  Good software is much more expensive and takes much longer to write.  But unlike most projects "out there", maintainable software can continue to grow.  Know what you're buying.  I've seen far too many people get "burned" because they spent thousands on a project that now must be rewritten because it wasn't developed for the long term the first time.

Moving on, there are certain principles and characteristics of maintainable software I'd like to expound on.  Some of these will fly directly in the face of practices common to the mobile community while some will be treading old ground.  Let's start with some "old ground":

####Unit Tests

Unit Tests is the thing everyone knows they should do, but a startlingly large number of developers avoid it and many that do add Unit Test only do so half-heartedly.  It's not surprising.  Unit Tests are _expensive_ and for most developers they're boring (probably the real reason for avoiding it).  Whenever you estimate the time it will take to complete a task, adding Unit Tests will generally _double_ that time.  

The advocates of Unit Testing (and I am one of them) contend that while Unit Tests do take time, they more than make up for it in saving later.  I can attest to this, especially in environments where the project undergoes a constant evolution of changes.  The risk of regression is real and Unit Tests become an essential check to make sure you're not breaking other parts of the code base.  

But regression isn't the only reason to Unit Test and, in my opinion, may not even be the main reason.  Personally, I've found that Unit Tests are a fantastic way to aid in the development process itself.  While I've never been able to go so far as the TDD camp (Test Driven Development) and write tests _before_ I develop the feature, I do utilitize what I would call TAD (Test Assisted Development), where the Unit Tests are written in parallel to development, as part of the development process.  I've frequently found Unit Tests indispensable when tackling tough problems as they make it easy to test assumptions I'm making in my code.  Developing in this way has often helped me avoid false developments paths by identifying incorrect assumptions early on in the development process.  This is much better than writing the entire class only to realize that it'll have to be rewritten because I forgot to account for "x".  Developing in this manner results in some unaccounted benefits, as it can really help you develop new features more efficiently.  

####3rd Party Frameworks

I risk stepping on a lot of toes here and garnering some significant push back, but generally 3rd party frameworks should be avoided.  There's generally only a couple reasons people use 3rd party frameworks: either they are required for some reason or the developer is looking for a shortcut.  Some frameworks can't be avoided: Crash Reporting, Analytics, and Service Integration SDKs (think Dropbox, Facebook, etc).  Other frameworks are purely for convenience or speed of development and _some_ of these are worth using.  AFNetworking, for instance, is widely used, well supported and reliable.  But with the advent of Cocoapods developers started adding frameworks for everything from Button Tinting and "ooo, I want the view to zoom in from the top" to more complex frameworks like React and others.  The temptation to "copy and paste" someone else's code is great, especially when there's pressure to perform.  But there are significant drawbacks that should always be weighed against the benefits, mostly that any 3rd party framework will detract from the project's overall maintainability.  

 - It's code that's not under your control developed by developers that don't necessarily adhere to your own standards, and even if they do now, there's no guarantee that they will continue to.  
 - Bugs and crashes in the code necessitate either waiting (hoping) the maintaining developers will fix it, or else fork off your own branch of the code base and maintaining it separately.
 - If you need additional features, you are again in the same boat as the above point: You either need to ask the developers to add it and then wait for them to do it, or else you'll have to fork off your own branch and add the feature.
 - Once you do fork a repository, it will begin to diverge from the original.  Over time, it will be more and more difficult to merge their changes into your own.  Eventually, it will become impossible and you'll essentially "own" their code, including all of their bad (and good) decisions.  
 - Importing code doesn't just import the features the code provides, but also all the decisions those authors made.  And so you implicitly accept all of their design choices, interaction paradigms, and architecture.  All of this will influence your code base, for better or worse.  Unfortunately, most developers don't really give this much though.  They use 3rd party code because it speeds up development and makes their job easier, but don't consider how it may be forcing incorrect architecture or design patterns on the project.
 - Most 3rd party code will be _more_ than you need.  At first glance, this may appear a good thing (it's there if we need it).  But again, most developers don't consider the additional _conginitive_ load that this will add in understanding, using and debugging both your code and the framework.  One key aspect of good software design is  _limiting_  the required cognitive load it takes to understand what a piece of code does.  You do this by limiting it's _possible interactions_ with other pieces of code.  When you introduce to one piece of code another piece of code that does too much, you must mentally filter all the interactions between these in order to understand what it happening.  And so: _code that does too much is  worse than code that doesn't do enough_.  

I need to be clear that I'm not proposing we should all get rid of every 3rd party framework and begin building everything from scratch.  That's insane (at the very least, we _have_ to depend on the platform we're developing for).  But it's important to understand the cost of adding 3rd party code and properly weigh that cost when deciding to add a framework.  One of the first things I do in any project is add `Crashlytics`.  If I needed networking, I used to add `AFNetworking`, but since Apple has improved it's networking frameworks lately, I'm not so sure it's needed as much anymore.  In these cases, the frameworks are highly supported and add excellent value (I have no intention of ever writing a crash reporting service... Ever).  But I've walked into projects that have 30 to 50 Cocoapods.  Don't do that... just, don't.

####Modules & Frameworks

Beginning in iOS 8, Apple added a fantastic new feature that allowed developers to start segregating the codebase into dynamic modules, which are essentially "in-project" frameworks, allowing the developer to split the project into discrete components.  Normally, these components represent a logical grouping of functionality and/or services.  Essentially, they operate like 3rd party frameworks you might import into the project, except they're code you write and they _are_ the project. This kind of separation of concerns is essential to maintaining a project.  You may notice, I have a tendency to harp on how dangerous complexity is to a project.  The more complex a project is, the more difficult it will be to maintain and alter.  Humans have only a limited ability to handle complexity, and it's quite easy for a project to exceed the ability of any human to hold the project's complexity in their head.  This is one of the reasons we "hide" complexity behind abstractions like a `class`.  As you compose the project, you need only think in terms of the abstractions (I have a bycicle that moves, I don't need to understand how all the components of the bicycle come together, I can just deal with the bicyle and forget about the complexity of it).  This gets to the heart of OOP (Object Oriented Programming).  But this principle extends to the project as a whole, where you end up with groups of classes that interact together to perform a function. The project only needs the function to be performed, so it doesn't make sense to expose all the underlying classes.  Those classes are placed in a framework or module and the project interacts with that abstraction.  The functionality can be developed in isolation of, and often in parellel to, the rest of the project.

As a project grows, eventually it will outgrow the scale that dynamic modules can handle.  At that point, it makes sense to create real, separate frameworks[^3], and import those frameworks back into the project using a dependency manager. This is particularly useful for larger teams, where multiple developers may be working in different parts of the project.  It help minimize conflicts and shortens the build times.

These are some guidelines I follow.  These are by no means rigid or even complete, and they're pre-disposed to a specific architecture, but they can be a great starting point:

- `Utilities`:  I generally have a framework devoted to the utilities I want made available to all other parts of the project.  These include things like common extensions to Foundation types, caches, custom operators, functional constructs, etc.  Note: I do not include anything specific to the UI because `Utilities` should be accessible to all parts of the app, including frameworks that have nothing to do with the UI.
- `Services`: I consider this more of a "layer", meaning there could be any number of frameworks that are "services" for other frameworks.  This would include things like `Networking`, `Per



[^1]: Or 90%... Or maybe it's 70%.  Honestly, I couldn't find a definitive number, which makes sense once I considered it.  Hell, the number could be 0% depending on what you're doing (all MVP projects).  So there are situations when you maybe should ignore this entire post because you (or anyone) _won't_ be maintaining the code.  However, it's sufficient to say that _if_ the code will be maintained, that maintanence will eat up increasingly large portions of your time as the project grows.
[^2]: Those who have "commissioned" the work and basically hold the risk: The company/person that hired you, or your manager, your boss, or even yourself (if you're writing your own app).
[^3]: At this point, there comes some serious considerations as to whether you want to also split these frameworks into separate _repositories_.  It might make sense, at first glance, to do this.  But it _will_ create more overhead for managing the project.  Because there will be dependencies between these frameworks and often a single "feature" or task will require changes in more than one framework.  At that point, you'll be trying to manage multiple, simultaneous change in the repositories and, depending on your work flow, PRs (if that's how you roll).  This can easily lead to frustration while you attempt to manage a "broken" project while trying to orchestrate all these changes.  Sometimes people forget that a repository doesn't have to be a single project.  By keeping multiple frameworks in a single repository you can submit and merge changes to multiple frameworks atomically, which is extremely useful.