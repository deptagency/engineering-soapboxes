# Efficiency as a programmer

📝 By [Simon][smonn]

[smonn]: https://github.com/smonn

---

Someone once said that a great programmer is a lazy one. The key being that they try to get as much done with as little effort as possible as opposed to not getting anything done. In other words, they are efficient. So what can you do to improve your efficiency?

## TL;DR

- Learn and use keyboard shortcuts
- Write less/more code
- Ask questions early and often
- Sometimes you just gotta RTFM
- Always be learning

## Learn and use keyboard shortcuts

This applies to any editor (or IDE). As soon as you find yourself doing something repetitive that _feels_ slow, try to find out if there's a keyboard shortcut for it. If not, can you add one?

For example, naming is hard. So eventually you'll want to rename a [symbol][symbol]. If your choice of editor includes some basic refactoring tools, chances are you can easily trigger a rename refactoring. In VS Code, _the best editor_, you can simply hit F2 with the symbol you want to rename selected. This should then update all references to that symbol to use the new name.

Getting familiar with a command-line-based editor like [Vim][vim] or [Nano][nano] is also highly recommended. Especially since those are very common to be installed by default in Unix-based operating systems. At minimum, learn [how to exit Vim][exit-vim]!

[symbol]: https://en.wikipedia.org/wiki/Symbol_(programming)
[vim]: https://www.vim.org/
[nano]: https://www.nano-editor.org/
[exit-vim]: https://exitvim.net/

## Write less/more code

You should write as little code as possible because that normally takes less time and effort than more complex code.

At the same time, [code golf][code-golf] practices, while entertaining, can sometimes make code hard to read and understand. Therefore, you may want to write slightly more code to more easily and effectively understand what the code does.

Knowing when to follow which of these two principles is a never-ending challenge.

On top of this, learning when to delete code is equally important. This mostly happens after refactoring and some code is no longer required.

In the end, the only code with 100% certainty will not contain bugs is code that doesn't exist. I recommend reading about the acronyms [DRY, WET, and AHA][dry-wet-aha].

[dry-wet-aha]: https://kentcdodds.com/blog/aha-programming
[code-golf]: https://en.wikipedia.org/wiki/Code_golf

## Ask questions early and often

Most would agree that making assumptions is bad. Sometimes it's necessary, but if you have a resource (could be a person, a book, data, etc) that can provide insight into the feature you need to build then go ahead and ask! The insight you may gather and the questions (and follow-ups) you ask will help both you and the end consumer.

What I've found to be the hard part is coming up with good and helpful questions. They say there are no stupid questions and chances are there's at least one other person in the room wondering the same thing as you. You just gotta have the guts to ask the "stupid" question.

Sometimes, it helps to figure out _what not to build_ and [asking why][ask-why]. Often it's easier to find the answer to what you don't need than the other way around.

As a developer/engineer, one key aspect of your role is to come up with solutions to problems and technical challenges. Asking questions will help you do just that.

[ask-why]: https://code.theothermattm.com/ask-why/

## Sometimes you just gotta [RTFM][rtfm]

Documentation is not always helpful. That's why I tend to pick libraries and services that provide better documentation than their competition. Good documentation is a joy to read and consume, and helps you get started within minutes. Bad documentation seems to try and prevent you from using the library/service. No offense to documentation writers, I know from experience it is a very hard task.

With that said, if you're stuck with using a library/service, just go ahead and look up the documentation (again, if needed). A few years ago I failed a code challenge just because I _thought_ I knew how to use a certain library. Be better than me and don't repeat my mistake.

[rtfm]: https://en.wikipedia.org/wiki/RTFM

## Always be learning

The best programmers I've met in my career have been multi-lingual. I'm not referring to speaking English and Swedish, but programmers who know more than one programming language and are quick to pick up (yet another) programming language. Features between languages don't _always_ translate well, but there are so many that are based on C that the bar for knowing at least two is very low.

The added benefit of knowing multiple languages, especially ones that use very different mechanisms, is that you can get ideas for how to solve a problem more efficiently in your daily language of choice.

Beyond that, learning some adjacent skills (be they hard or soft skills) is always beneficial both to your efficiency but even more so to your career long term. Knowing every detail of 20 programming languages is neat, but knowing some basic DevOps, how projects are managed, maybe some basic design skills, etc will open up so many opportunities.

So subscribe to newsletters, take an online course, follow some "thought leader" blogs/Twitter accounts, and keep up with your favorite libraries and/or services by reading source code and release notes. There's always something new to learn and that is awesome.
