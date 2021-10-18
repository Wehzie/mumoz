# Multimodal Zettelkasten (Mumoz)

## Features

- Architecture after Luhmann's Zettelkasten.
    - The Zettelkasten method in [English](https://zettelkasten.de/posts/overview/).
    - The Zettelkasten method in [German](https://niklas-luhmann-archiv.de/nachlass/zettelkasten).
    - Another term for the Zettelkasten is the [Second Brain](https://www.buildingasecondbrain.com/).
- Current implementations.
    - A [Java](http://zettelkasten.danielluedecke.de/) implementation of the Zettelkasten with an old-school user interface.
    - [Neuron](https://github.com/srid/neuron), a Haskell implementation. Very cool project, also uses [Nix](https://nixos.org/) and [Matrix](https://matrix.org/). [Emanote](https://github.com/srid/emanote), a currently, seemingly, less popular successor to Neuron by the same author.
    - [Obsidian](https://obsidian.md/) is a proprietary, cross-platform, markdown-based note taking tool. With a focus on cross-references and building a knowledge graph it's similar to the Zettelkasten. Other similar proprietary apps are [Notion](https://www.notion.so/) (client is open source), [Roam Research](https://roamresearch.com/), [RemNote](https://www.remnote.com/) with support for flash cards.
    - [Foam](https://github.com/foambubble/foam) is a Roam based VSCode extension.
    - Don't allow linking to subsections of a Zettel. A Zettel should be atomic and KISS.
- Editor.
    - Reuse what exists, keep it simple.
    - The editor should not be the focus of this project.
    - The system should be usable even when limited to only sending text messages to your Zettelkasten.
    - The system should feel as plastic and haptic as possible.
    - [VSCode](https://code.visualstudio.com/) is a dekstop and web supported text-editor with extensions.
    - [Zettlr](https://github.com/Zettlr/Zettlr) is a desktop-only TypeScript based Zettelkasten enabled Markdown note-taking app.
    - [Joplin](https://github.com/laurent22/joplin/) is a web-mobile-desktop TypeScript-based note taking app with paid syncing options. [Standard Notes](https://github.com/standardnotes) seems similar but a bit worse.
    - [FSNotes](https://github.com/glushchenko/fsnotes) is a iOS and Mac only note taking app in Swift.
    - 3D representation and VR with the Zettelkasten.
- Export and import to and from many formats.
    - Import from a collection of .md files such as maintained with Obsidian.
    - Import from a loose collection of data .odt, .doc, docx. Use NLP and clustering for creating Zettel.
    - Import from services such as EverNote, OneNote.
    - Export entire Zettelkasten.
        - To database dump.
        - To collection of markdown files.
        - To a single PDF or to a collection of PDFs by filters.
        - To EPUB.
        - To JSON.
- Visualization: Support for mind map or tree generation.
    - Visualize markdown as a tree. Implemented in [Typescript](https://github.com/gera2ld/markmap).
        - Available as extension in [VSCode](https://marketplace.visualstudio.com/items?itemName=gera2ld.markmap-vscode).
    - Mind map software in [Javascript](https://github.com/ondras/my-mind).
    - Alternative mind map software in [Javascript](https://github.com/drichard/mindmaps).
    - [Diagrams.net](https://github.com/jgraph/drawio) formerly Draw.io is a general purpose diagramming software.
    - Visualization should allow (1) eagle-view of all nodes (2) filtering for incoming nodes of some node (3) filtering for outgoing nodes of some node.
    - 3D-printable topological map of the Zettelkasten.
- Learning: Support for flash card generation.
    - Memcode is a flashcard webapp written in [Javascript](https://github.com/lakesare/memcode).
    - Anki consists of an open source [desktop app](https://github.com/ankitects/anki), [Android app](https://github.com/ankidroid/Anki-Android), and a proprietary [web app](https://ankiweb.net/about) and [iOS app](https://apps.apple.com/us/app/ankimobile-flashcards/id373493387).
    - AI-feature to convert a Zettel to a closure flashcard or to formulate a question that is answered by the Zettel. Separate label for AI-generated questions/closures. Allow regeneration and user-selection of best generation.
    - Active recall learning with spaced repetition on a subset of Zettel.
- Blogging: Support for publishing a collection of Zettel to the web.
    - See this [example](https://alien-psychology.zettel.page/) generated from notes about a TV-show using the Neuron app.
- Search and filtering.
    - Test multiple search algorithms.
    - Strive for something like Google's MUM: Multimodal search with for example auto-generated labels for images in a Zettel.
    - Chronological view of the Zettel creation history.
    - Visualization of meta-information. For example zettel creation frequency.
- Labels/Tags as feature-controllers and as filters for a Zettel.
    - Example: filtering by a diary-label, university-label or a specific course-label.
    - Example: Generating a Flashcard from a Zettel should only be possible when a flashcard-label is present and a question or closure can be located on the Zettel. 
- Support for news.
    - Receive updates on topics inside your Zettelkasten from the Web.
    - Configure sources: Google, Google Scholar, Reddit, NY Times, The Economist, Twitter, Nature, Science, The Lancet.
    - Receive news from (1) manually selected and filtered Zettel (2) most recent Zettel (3) most connected Zettel (4) most referencing Zettel (5) most referenced Zettel.
    - Automatic Zettel creation from a news article using AI an generated modifiable summary. Includes automatic reference to article.
- Multi-modal data support: vector-graphics-canvas, text, 2D images, 3D images, latex, code, audio, 2D video, 3D videos.
    - In the long run, code execution for many programming languages could be possible with WebAssembly.
    - AI tools to generate multi-modal. For example automatic transcription of voice recordings.
    - Integrate arbitrary external documents.
        - Example: Allow loading a paper's full PDF into the database. Clicking on a reference then opens the PDF.
- Multi-note and multi-user support for synchronous and asynchronous editing.
    - View, edit and delete multiple local Zettel at the same time.
    - Share Zettel with other users. Push and pull synchronization similar to git with remote Zettelkasten.
    - Mount remote Zettelkasten giving the option to pull. Or clone making an independent, non-updating copy. Automatic cache before pulling with option to sever ties to remote Zettelkasten on a given set of nodes.
- Uses a database to grow a lifetime.
    - [SQlite](https://www.sqlite.org/index.html) is a database but not overkill. Concurrency relies on file-locking. This is [acceptable](https://stackoverflow.com/questions/5102027/can-sqlite-support-multiple-users) for a small number of concurrent users. 
- Prototype/MVP in HTML, CSS, Javascript targeting web.
    - Could be packaged with [Electron](https://github.com/electron/electron) for desktop apps.
    - Could be packaged with Ionic's [Capacitor](https://github.com/ionic-team/capacitor) for mobile.
- VR.
    - There is a rich ecosystem of note taking, learning, productivity management, knowledge management and collaboration apps.
    - VR will grow a lot in the future.
    - Remove tradeoffs between the physical and the digital Zettelkasten.
    - Visualizations and knowledge in the 3D dimension are more comprehensive.
- An advanced app could be in Dart/[Flutter](https://flutter.dev/) targeting mobile, desktop, web.
- Cross-platform and synchronized.
    - Centralized synching as a service.
    - Centralized synchronization via external Clouds such as Nextcloud, Dropbox, Google Drive, iCloud, OneDrive.
    - Local syncing via [Syncthing](https://github.com/syncthing/syncthing).
- Grammatical note: In German's Nominative case it's "1 Zettel, 2 Zettel" but English doesn't have cases and "1 Zettel, 2 Zettels" sounds kind of natural in English.

## Conclusion

Either make plugins for Joplin because it's open source and cross-platform. This gives independence to develop the features next to Joplin. Or use a script like [this](https://gitlab.com/annyong/baeuda) to generate flash cards. Do plugins work on mobile?

Or extend Joplin, however it's unlikely that Joplin core would want all those features.

Or use Obsidian because it looks so good and while it doesn't have flashcards.
And extend Obsidian with a script to generate flashcards from the markdown files. However this is not truly cross-platform.

Or make a new product. This is the only approach that can be taken to implement all functionality. However implementing all features is a mammoth task. Maybe forking Joplin is an option. A new product in Flutter/Dart would produce a prettier and faster mobile app. However Obsidian uses the JavaScript ecosystem and that app seems good.

A key differentiation could be a free canvas environment similar to OneNote; however there is no good standard for this. Markdown by contrast is a clear standard.

Or study for your exams.