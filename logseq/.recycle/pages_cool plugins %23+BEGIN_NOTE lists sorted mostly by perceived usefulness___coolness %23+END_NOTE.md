- #+BEGIN_NOTE
  lists sorted mostly by perceived usefulness/coolness
  #+END_NOTE
- for taking notes/data ingestion
	- videos
		- ?[whisper-subtitles](https://github.com/usoonees/logseq-plugin-whisper-subtitles)
		  :LOGBOOK:
		  CLOCK: [2024-12-17 Tue 11:30:56]--[2024-12-17 Tue 11:30:57] =>  00:00:01
		  :END:
		- [helium: a Logseq plugin to float items (e.g. videos) for an improved note-taking experience](https://github.com/vyleung/logseq-helium-plugin)
	- webpages
		- TODO https://github.com/pomali/logseq-plugin-automatic-url-title install/test this and publish the forked version
		  collapsed:: true
			- TODO needs a command to toggle itself on/off for when it's not needed
			  :LOGBOOK:
			  CLOCK: [2024-12-17 Tue 20:46:18]--[2024-12-17 Tue 20:46:20] =>  00:00:02
			  CLOCK: [2024-12-18 Wed 01:54:34]--[2024-12-18 Wed 01:54:36] =>  00:00:02
			  CLOCK: [2024-12-18 Wed 01:56:35]--[2024-12-18 Wed 01:56:37] =>  00:00:02
			  :END:
			- TODO needs settings for regex replacement rules- for modifying both the url and the title based on the html content D:
				- stripping the site name for certain sites (usually we can already tell from the favicon)
				- appending (or even sub-pending) relevant context for e.g. twitter embeds. since we're making the request already
					- would mean merging this plugin into ((6761960a-2ec4-462a-8e10-7a28dbaf60d8))
				- sites i like to use, each one needs a regex rule
					- DOING bsky.app
					  :LOGBOOK:
					  CLOCK: [2024-12-18 Wed 01:49:53]--[2024-12-18 Wed 01:49:55] =>  00:00:02
					  CLOCK: [2024-12-18 Wed 01:54:26]--[2024-12-18 Wed 01:54:31] =>  00:00:05
					  CLOCK: [2024-12-18 Wed 01:54:31]
					  :END:
					- TODO x.com
					- TODO discord.com
					- TODO reddit.com
					- TODO tumblr.com
					- TODO t.me
					- TODO github.com
		- [logseq-archive-webpage](https://github.com/patmigliaccio/logseq-archive-webpage) archive URLs with web.archive.org and locally as html
		  id:: 67613b07-1c02-4d64-b748-35b1a52ada3b
		  collapsed:: true
			- TODO add functionality to request a crawl if there isn't one already.
				- don't forget to convert reddit links into old.reddit.com links before requesting
					- maybe other alt frontentds?
		- [logseq-web-parser](https://github.com/sawhney17/logseq-web-parser) attempts to parse a webpage into markdown block(s)
		  id:: 676141f7-e755-4a5b-8f59-3e83660c0bc9
			- TODO option to put open graph fields (or other meta info gleaned from html tags?) into block children or block properties
			- [logseq-recipeimporter-plugin](https://github.com/hkgnp/logseq-recipeimporter-plugin) same thing but specifically for recipes
	- specific services
		- [logseq-hypothesis](https://github.com/c6p/logseq-hypothesis)  plugin for hypothes.is
		- [logseq-inbox-telegram-plugin](https://github.com/shady2k/logseq-inbox-telegram-plugin) fetch from a telegram bot. requires heroku
		- [logseq-tweet-extractor](https://github.com/sawhney17/logseq-twitter-extractor) parse tweets into custom template
		  id:: 6761960a-2ec4-462a-8e10-7a28dbaf60d8
		- ?[logseq-github-plugin](https://github.com/sawhney17/logseq-github-plugin) fetch/parse stuff from github like active issues etc
		  collapsed:: true
			- [logseq-show-github-star](https://github.com/studyduck/logseq-show-github-star) renders star counts on github repo urls
			  collapsed:: true
				- TODO only show stars on top level repo urls, not subpages
		- ?[logsync](https://github.com/clstb/logsync) github and ical
		- ?[logseq-koreader-sync](https://github.com/isosphere/logseq-koreader-sync) sadly one-way (down) (for now)
		- ?[logseq-trello-plugin](https://github.com/jarodise/logseq-trello-plugin) two-way sync
		- ?[logseq-nostr-sync](https://github.com/KoalaSat/logseq-nostr-sync) one-way (down)
		- wishlist for more services
			- {{embed ((676301a9-2fb0-4f3e-ae75-b8b7225b2d25))}}
- organization in general. most of these should really be merged into the main app imo
	- navigation
	  id:: 676185bd-6d4e-423d-8294-3c1ad139ee5b
		- [logseq-plugin-jump-to-block](https://github.com/freder/logseq-plugin-jump-to-block) search and scroll to a block, unfolding as needed
		  id:: 676202f0-06eb-4c08-a4ba-bfccfdf0aa4f
		  collapsed:: true
			- TODO make the window resizeable. want it huge and near centered
			- TODO enter key opens the first result
			- TODO when previewing results, save the original scroll position (and focus target) and go back to it when cancelling the jump
			- TODO add case sensitivity and maybe regex
			- uses a [custom scrollTo function](https://github.com/freder/logseq-plugin-jump-to-block/blob/e4a1374495b12e16d9ec4e9044467d63b083de78/src/components/App.tsx#L29).
			  id:: 676301aa-0bd2-4dd0-af07-94ce723d1be3
				- except how does it unfold folded blocks??
		- [logseq-save-scrollbar-position](https://github.com/studyduck/logseq-save-scrollbar-position) preserves scroll position when navigating
		  id:: 67618731-9058-485d-84ee-7da166efec6a
		- alternate views
			- ?[logseq-classy](https://github.com/mlanza/logseq-classy) Facilitates otherwise impossible custom stylesheets by applying classes to blocks identified in custom queries.
			  collapsed:: true
				- ?[logseq-style-carousel](https://github.com/mlanza/logseq-style-carousel) Add button(s) for stylesheet-driven effects such as toggling the visibility of completed to-dos. depends on:
			- ?[logseq-filterpage-plugin](https://github.com/benjypng/logseq-filterpage-plugin) Quickly filter the current page based on tags that you want to include or exclude. only a plain filter, but with arbitrary value
			- [logseq-plugin-mark-map](https://github.com/vipzhicheng/logseq-plugin-mark-map) mind map view
			  collapsed:: true
				- TODO css should be moddable, looks too cramped by default
				- TODO more keyboard controls
					- command for editing a block
					- a way to show the logseq context menu would be ideal
			- ?[logseq-graph-analysis](https://github.com/trashhalo/logseq-graph-analysis) Learn more about the relationships between between your notes using network analysis algorithms.
			- ?[GitHub - cannibalox/logtools](https://github.com/cannibalox/logtools) utilities for kanban chart, image gallery, numbered lists with numbered subsections (!), etc. see readme
			  collapsed:: true
				- ((676199c1-c0a0-42de-839e-7781f134d629)) has kanban and gallery views as well
			- ?[logseq-custom-files](https://github.com/cannibalox/logseq-custom-files) resizable query results columns, better twitter embeds, better sidebar
			- [logseq-toc-plugin](https://github.com/benjypng/logseq-toc-plugin)
	- block manipulation
		- ?[logseq13-missing-commands](https://github.com/stdword/logseq13-missing-commands) lots of stuff, see readme
		  id:: 676199c1-c0a0-42de-839e-7781f134d629
		- ? [logseq-quick-add-plugin](https://github.com/vyleung/logseq-quick-add-plugin)  commands to add and duplicate blocks and insert current time
		  collapsed:: true
			- [logseq-datetag-plugin](https://github.com/sawhney17/logseq-datetag-plugin) append the creation date of a block as a tag. Requires block timestamps to be enabled in settings. obsolete in db version
			  collapsed:: true
				- TODO merge this function into [logseq-quick-add-plugin](https://github.com/vyleung/logseq-quick-add-plugin)
		- [logseq-move-block](https://github.com/vipzhicheng/logseq-plugin-move-block) move selected blocks to another page
		- [logseq-swapblocks-plugin](https://github.com/benjypng/logseq-swapblocks-plugin) swap a reference and its target
		- ?[logseq-extract-plugin](https://github.com/sidharth-panwar/logseq-extract-plugin) extract bold and highlighted text from a block and all its nested blocks.
		- [logseq-quick-date](https://github.com/13hannes11/logseq-quick-date) commands to insert relative date, such as 'Last Wednesday' and 'Next Friday'
		  collapsed:: true
			- TODO extend to add days of the month, not just next/last week
	- block presentation
		- [logseq-bullet-threading](https://github.com/pengx17/logseq-plugin-bullet-threading) Add threading indicators to your active block
		  collapsed:: true
			- trivia: made by the first [logseq hobbit](https://pengx17.vercel.app/posts/my-logseq-contributions)
			- TODO make it work with the focused block even when not in edit mode
		- [logseq-copy-code-plugin](https://github.com/vyleung/logseq-copy-code-plugin) Copy code from code blocks to your clipboard
		- [logseq-plugin-show-page-date](https://github.com/YU000jp/logseq-plugin-show-page-date) show creation and modification dates on pages.
		- [logseq-randomutils-plugin](https://github.com/benjypng/logseq-randomutils-plugin) useful for dictionary lookup and google search commands
		  collapsed:: true
			- TODO also has redundant styling and block manipulation commands. fork it and remove the redundant ones
		- [logseq-copy-url](https://github.com/RubenSmn/logseq-copy-url) adds copy button to links
		- [logseq-plugin-link-preview](https://github.com/pengx17/logseq-plugin-link-preview) adds opengraph previews
- todos and time management
  query-table:: false
	- automation
	  collapsed:: true
		- [logseq-task-automation](https://github.com/aiirobyte/logseq-task-automation)
		  collapsed:: true
			- auto toggling parent doesn't work :| #bug
			- neither do the commands (they use the [[manual command config]]) #bug
	- [logseq-todo-plugin](https://github.com/haydenull/logseq-plugin-markdown-table) quickly search your TODO items and easily add one to today's journal page
	- ?[logseq-pomodoro-plugin](https://github.com/sawhney17/logseq-pomodoro-plugin) pomodoro timer
	- completion date (figure out which works better)
	  collapsed:: true
		- ?[logseq-plugin-task-check-date](https://github.com/DimitryDushkin/logseq-plugin-task-check-date) adds 'completed: <today's date>' property to task upon checking. See README for report generation query.
		- ?[logseq-plugin-confirmation-done-task](https://github.com/YU000jp/logseq-plugin-confirmation-done-task)
		- ?[logseq-task-done-time-mtini](https://github.com/mlhiter/logseq-task-done-time-mini) [readme](https://github.com/mlhiter/logseq-task-done-time-mini/blob/master/README.en.md)
	- ? [logseq-cycle-todo-dwim](https://github.com/hron/logseq-cycle-todo-dwim)  Cycle TODO state (Do What I Mean) Ctrl+Enter with repeating timestamp support, similar to org-mode
	- visualization
	  collapsed:: true
		- ?[logseq-plugin-better-tasks](https://github.com/dsarman/logseq-plugin-better-tasks) changes parent task to `doing` when at least one child is `doing`, could be in ((676185bd-6d4e-423d-8294-3c1ad139ee5b))
		- [logseq-plugin-todo-master](https://github.com/pengx17/logseq-plugin-todo-master) simple progess bar of all tasks on page
	- [logseq-todo-exploder](https://github.com/sawhney17/logseq-todo-exploder) confetti on completed todos :)
	  collapsed:: true
		- laggy on my machine :(
		  :LOGBOOK:
		  CLOCK: [2024-12-17 Tue 18:23:36]--[2024-12-17 Tue 18:23:37] =>  00:00:01
		  :END:
- support for specialized formatting
	- [logseq-markdown-table](https://github.com/haydenull/logseq-plugin-markdown-table) Markdown Table Editor
	- ?[logseq-discourse-graphs](https://github.com/sawhney17/logseq-discourse-graphs) Discourse Graph workflows in Logseq
	- ?[logseq-plugin-areas](https://github.com/bsongOT/logseq-plugin-areas) area maps. whoa
	- ?[logseq-mermaid-plugin](https://github.com/benjypng/logseq-mermaid-plugin) mermaid diagrams
	- ?[logseq-preview-footnote](https://github.com/b-yp/logseq-preview-footnote) footnote with hover preview
	  collapsed:: true
		- this should be a special syntax for a reference alias actually. [alias](((67613b07-1c02-4d64-b748-35b1a52ada3b)))
- integrate with other apps
	- [logseq-open-in-code](https://github.com/rebornix/logseq-open-in-code) open file or graph in vscode. useful for find and replace
	  id:: 676186f2-ba8d-49ee-ab61-62d4ea805538
		- TODO add keyboard shortcuts
		- TODO should be generalized for other apps too
	- [logseq-plugin-git](https://github.com/haydenull/logseq-plugin-git) git commands from logseq
		- kinda buggy tbh.
		  collapsed:: true
			- TODO better to set up github hooks to auto sync every commit (for data safety)
			- TODO also a custom script to close logseq and open a git client to squash/cleanup the history.
	- TODO asset manager? figure out which is better
		- ?[logseq-plugin-file-manager](https://github.com/haydenull/logseq-plugin-file-manager) A file manager plugin for logseq (Search unused assets file).
		- ?[GitHub - benjypng/logseq-localassets-plugin](https://github.com/benjypng/logseq-localassets-plugin)
		- ?[GitHub - YU000jp/logseq-plugin-multiple-assets: Save multiple files into assets](https://github.com/YU000jp/logseq-plugin-multiple-assets)
- TODO look at possible cool plugins by
  :LOGBOOK:
  CLOCK: [2024-12-17 Tue 20:06:27]--[2024-12-17 Tue 20:06:28] =>  00:00:01
  CLOCK: [2024-12-18 Wed 01:57:18]--[2024-12-18 Wed 01:57:20] =>  00:00:02
  CLOCK: [2024-12-18 Wed 01:57:21]--[2024-12-18 Wed 01:57:23] =>  00:00:02
  :END:
	- TODO @hkgnp
	  :LOGBOOK:
	  CLOCK: [2024-12-18 Wed 01:57:14]--[2024-12-18 Wed 01:57:24] =>  00:00:10
	  CLOCK: [2024-12-18 Wed 01:57:27]--[2024-12-18 Wed 01:57:31] =>  00:00:04
	  CLOCK: [2024-12-18 Wed 01:57:36]--[2024-12-18 Wed 01:57:39] =>  00:00:03
	  CLOCK: [2024-12-18 Wed 01:57:39]--[2024-12-18 Wed 01:58:22] =>  00:00:43
	  CLOCK: [2024-12-18 Wed 01:58:24]--[2024-12-18 Wed 01:58:25] =>  00:00:01
	  CLOCK: [2024-12-18 Wed 01:58:28]--[2024-12-18 Wed 01:58:35] =>  00:00:07
	  CLOCK: [2024-12-18 Wed 01:58:38]--[2024-12-18 Wed 03:14:29] =>  01:15:51
	  :END:
	- TODO @vipzhicheng
	  id:: 6761b414-58af-4302-8fb3-377436ac9687
	  :LOGBOOK:
	  CLOCK: [2024-12-17 Tue 20:06:42]--[2024-12-17 Tue 20:06:45] =>  00:00:03
	  :END:
	- TODO @yoyurec
	  :LOGBOOK:
	  CLOCK: [2024-12-17 Tue 20:06:45]--[2024-12-17 Tue 20:07:13] =>  00:00:28
	  :END:
	- TODO @Aryan Sawhney
- TODO automate looking at all plugins with data from github.
	- https://xyhp915.github.io/logseq-marketplace-table/