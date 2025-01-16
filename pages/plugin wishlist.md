- (roughly sorted by estimated ease of implementation and desirability)
- missing commands:
	- toggle folding of the Xth level of current block or document
		- more complex: also command to toggle fold of the deepest level that isn't entirely folded/unfolded. enables neat flow where you can progressively (un)fold children level by level
	- go to next same-level block (as selected one)
	- command to quickly preview a block in a reference (with context and children
	  :LOGBOOK:
	  CLOCK: [2024-12-19 Thu 13:17:36]
	  :END:
		- TODO there's already a mouse hover preview for references that displays the block in editable form - figure out how to invoke it from keyboard.
	- select original ancestor block (so you don't have to use ctrl-a like 6 times you're deep in the weeds)
	- select and unindent all immediate children of a block
		- on repeated invocation, unindent its grandchildren and so on
	- inputting quotes while a string is selected wraps the string in quotes.
	  id:: 67631850-7c5e-441d-a8f8-36cca93058a3
		- [sethyuan really was holding up half of logseq's basic functionality, please come back man. left-pad moment](https://discord.com/channels/725182569297215569/752845167030960141/1199153970833281145)
		- already implemented in "magic quotes" command of ((676199c1-c0a0-42de-839e-7781f134d629)), just need to make it kick in passively
	- pasting content on an focused block (while in view mode) block pastes the content as a new block under it
	  id:: 676301a9-62b5-42d7-b88d-d516bc4ec0ef
- "polyfill" for ((676200f1-1f67-44c0-94e7-6500a19672f4)). can be based on ((676301aa-0bd2-4dd0-af07-94ce723d1be3))
	- related: command/config option to increase default context displayed when jumping to a block from a plain link
	  collapsed:: true
		- this wouldn't be the same as just showing the block in the page, but a special view with just the parents (no siblings)
- ((676f3c79-aa49-41ee-8edf-67e7bbaa7afd))
- a way to filter out hunks that are just for collapsing/expanding in git autosaves. either a plugin mod or a python script in a commit hook (when using external git)
- truncate long formatted urls when editing. putting the cursor on the url expands it.
  collapsed:: true
	- i generally hate rich-text/wysiwyg editing but making an exception here
- tampermonkey D: we already have custom.js this would just make it easier to manage
	- mostly i want [github hovercards](https://github.com/Justineo/github-hovercard)
- display navigation history when long pressing the back/forward buttons like in a web browser
- "lock" a block to prevent accidental edits
- more specific versions of ((676141f7-e755-4a5b-8f59-3e83660c0bc9))
  id:: 676301a9-2fb0-4f3e-ae75-b8b7225b2d25
  collapsed:: true
	- TODO these can probably be implemented in ((677407a1-9cf0-4e56-833b-b96a6b37b71e))
	  ask stdword on discord!
		- TODO use the site's rest api when available
	- sites
		- rss/atom
			- [logseq-rss-reader](https://github.com/b-yp/logseq-rss-reader) is not it (modal reader, not blocks embed) but maybe worth checking out the libs used
		- web hosted logseq pages
		- bluesky
			- https://github.com/callmephilip/bsky2md
		- hackernews
		- mastodon
		- lemmy
		- reddit
		  id:: 6764239e-f627-4646-bc65-447f48cefa43
		- tumblr
		- lobste.rs
		- github
			- lists and repos