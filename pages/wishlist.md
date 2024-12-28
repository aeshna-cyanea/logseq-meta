- bugs and basic borked functionality
	- navigation
		- ctrl-k annoyances
			- block search matches should be above the create page button!! if there is a matching block i'm hell of a lot more likely to want the match than to make a new page
			- navigating to a result should work like this plugin ((676202f0-06eb-4c08-a4ba-bfccfdf0aa4f)) except across pages ofc
			  collapsed:: true
				- it has much better navigation within a page than the command palette, which always zooms in when focusing on a block.
				  id:: 67620c49-6c6c-4d1d-840a-8ab35ecd0b4c
				  losing visual context (from unexpected page jumps) sucks so bad.
					- when i "go to" a block that is on the same page as the current one, it should just scroll to that block. i can decide myself whether to zoom in after
		- is there no keyboard based way to navigate up out of a zoomed in block unless you're in edit mode?
			- the command is called "Zoom out editing block / Backwards otherwise" and it works (in edit mode)
				- but when not in edit mode it doesn't even go back!
				- really these commands should be split and "zoom out/go to parent block" should work in view mode as well
					- ((676199c1-c0a0-42de-839e-7781f134d629)) has an action for this, could maybe be patched. "zoom out" and "scroll to parent" should definitely be a single command
		- find prompt
			- ["Find in page" does not focus the find prompt if it is already open unfocused](https://github.com/logseq/logseq/issues/8360)
			- does not display all matches in the scroll bar like a modern browser
			- does not support regex (ok this is optional, but the first two are kinda necessary)
	- text editing
		- ((67631850-7c5e-441d-a8f8-36cca93058a3))
		- ((676301a9-62b5-42d7-b88d-d516bc4ec0ef))
		- sometimes undoing doesn't work [related feature request](((6767da5c-d6d9-43c1-912c-11bdea91ab6a)))
		- clicking on a block doesn't always put the cursor where you clicked, sometimes it gets put at the beginning or end. very annoying and probably fixable
	- other (sorted by annoyance level):
		- [aliases are always visible on graph](https://discuss.logseq.com/t/improve-implementation-of-aliases/81/40) [matching github issue](https://github.com/logseq/logseq/issues/4709)
		- deleting the top level block from inside an embed should also kill original block "in real life".
			- this should delete the embed at the source too.
				- if the block that contained the embed contained nothing else, delete the whole block too
			- note: deleting children already works as expected (updates original's children) but not the top level of the embed
		- there is global.edn but no global.css?
			- you can `@import url("../assets/custom/header_label.css");` but i [had to google for it](https://discuss.logseq.com/t/custom-css-cant-import/3297/4).
				- TODO proposal: just have a global.css and have it be imported by default in new graphs. it's silly having to define an import (even to a relative path) for every graph.
		- TODO footgun: `ctrl-r` should not be bound by default to reload. doesn't this cause data loss? make it `ctrl-shift-r`
		- timestamp support for local audio and video files, not just youtube. we're a "local first" app after all. [another sethyuan moment](https://web.archive.org/web/20240826181136/https://github.com/sethyuan/logseq-plugin-media-ts/blob/master/README.en.md)
		  id:: 676f3c79-aa49-41ee-8edf-67e7bbaa7afd
	- TODO github search for all of these. i bet they all have long standing issues
		- also search for prs from bad3r on discord. they seem to have their head on their shoulders and a lot of good ideas for fixing basic broken stuff
	- [user perceptions of tech debt](https://old.reddit.com/r/logseq/comments/1cc6jiz/the_logseq_team_is_a_terrible_steward_of_logseq/l1kvi9t/) (this comment is relatively friendly, the rest of the thread is pretty mean)
		- they do kinda raise a valid point, the development of rum is really slow - no releases in years. If logseq is so active (and very demanding performance wise), why aren't they contributing patches upstream?
- unify and properly document commands
	- we have all three: keyboard shortcuts, command palette, slash commands, macros
		- and no clear way to link them up! vscode does it so much better! like them, we should be able to assign a keybind while looking at the command in the command palette or a context menu
			- when displaying source of a command, drop `$plugin.` and `-plugin$`
			- some plugins define shortcuts with plaintext in their settings!! this makes you very confused when the command doesn't show up in the default interface!!
			  id:: 6761f67c-8346-43e3-9aa5-9cd9faf8c1ce
				- for example ((676186f2-ba8d-49ee-ab61-62d4ea805538))
		- we should be able to edit the block context menu in a config file. some extensions don't need a context menu item because we already use their keyboard shortcut. context menu only for rarely used stuff
		- we should be able to filter by categories of keybinds when searching in the keybind config
			- maybe also split up keybinds between view mode and edit mode? #proposal
- a way to quickly look at the undo buffer. sometimes undoing an action doesn't work and this would at least help restore some context/debug what is missing
  id:: 6767da5c-d6d9-43c1-912c-11bdea91ab6a
	- ideally, a full emacs-style undo-tree. some wonderful guy tried and failed to get it into vscode (after a valiant attempt, see [the back and forth on this issue](https://github.com/microsoft/vscode/issues/20889)). We can (un)do better!
- extension controls. we should be able to:
	- rearrange extension buttons with drag and drop
	- let extensions define custom behaviour on alternate clicks on their button(right, middle) and while holding mod keys.
		- but reserve shift-rightclick for a system context menu with option to configure/disable/remove
- better links
	- #proposal: why not use urls everywhere instead of ids? would be better when viewing with other tools
	  id:: 676413a6-a313-4677-8611-247978e87c36
	- params for internal links
		- link to blocks in context
		  id:: 676200f1-1f67-44c0-94e7-6500a19672f4
			- we already have deeplink syntax zoom in on a block, but we need syntax to link to a block so that when clicked it's shown in X levels of context and selected. like ?context=9 link param for reddit comments
			- embedding such a link should work too, so that the link is displayed with its parents.
				- then if it gets moved, the parents are updated!
		- "quietly" link to a page such that the edge doesn't show up in graph visualization
		  id:: 676200f1-fb2a-4c1f-a4de-ea3294bc7d06
- add an option to make automated scrolling instant, but have the scrollbar catch up smoothly while leaving a visual "shadow" at its point of origin.
	- this way i can get to my content instantly when i know where i'm going, but if i'm taken somewhere unexpected (either bug or fatfinger) then i can check the scrollbar to see where i came from and reorient
- support for end-user "literate programming" (as prohesied by maggie appleton)! macros but actually cool. This is a big draw of emacs/org-mode and we should do more to exploit the fact that we're working in cljs.
	- ui description
		- a block could have a button to attach a codeblock of javascript or clojurescript (with included query capability, access to logseq features, functions from plugins, etc) and a "run" button
			- needs to be safe
				- possibly have the script sandboxed to that block and its children
				- automatically save to disk beforehand! display a diff of the file afterward!
			- you could have a ui toolkit as well for user input mid-script
			- could also have an api to register a command (remember, erase the difference between / commands and command palette) to run that same clojurescript from elsewhere on the currently focused block
				- or if multiple blocks are focused, on their common (grand)parent
		- the vibe should be that it is low friction, easy to define and run!
		  scripts can be attached to a block, deleted after one use, or stored in a userscript manager (e.g. tampermonkey) style interface for later reuse
	- so this already exists but seems really clunky to use https://docs.logseq.com/#/page/clojurescript%20eval%20in%20a%20block
		- needs better docs! this user promised but never delivered. some examples upthread tho https://github.com/logseq/logseq/pull/7287#issuecomment-1322859418 gotta read/document those
id:: 676301a9-6b2a-40c7-a287-882264bf0383
			- more prior art?
				- use in queries? https://discuss.logseq.com/t/more-function-in-advanced-query-runtime/22975
	- examples
		- i was saving a lot of links from a website and needed to reformat them based on the content
		  this meant requesting the html of each one, finding a specific dom element, append its contents to the block
			- i know python and it would have been a fairly quick python script (with the appropriate libraries)
				- TODO hmm is there a python parser for logseq-flavored markdown that turns it into a structured tree, and then puts it back into markdown after i'm done editing. then i could just run the python on my files. is this it? https://github.com/logseq/nbb-logseq gotta ask around
		- ((676301a9-6b2a-40c7-a287-882264bf0383))
		  :LOGBOOK:
		  CLOCK: [2024-12-19 Thu 12:00:12]--[2024-12-19 Thu 12:00:13] =>  00:00:01
		  :END:
- deeplinks for plugin store pages (for easy installation)