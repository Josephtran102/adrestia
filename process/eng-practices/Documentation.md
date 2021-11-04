---
tags: [ needs/review ]
tags: [process]
---

# Documentation Guidelines

Documentation helps us work more effectively.

It can clear doubts from people's minds and frees us from the need to explain
the same things repeatedly.

The act of writing documentation helps us understand things more clearly
ourselves. If we can't explain something in words, then it probably doesn't make
sense.

Documentation helps us understand historical reasons for why things are like
they are, especially when the pages are stored in Git repositories.

## Something is better than nothing

Remember that it's better to have _some_ information, rather than none at all --
providing that it's _correct_ of course.

Documentation doesn't need to be perfect. Just write something. It can be
improved and expanded upon later.

Don't worry too much about using correct English if it's hard. On the other
hand, if you find some spelling mistakes or odd sentences in our docs, and you
know how to fix them, then just go ahead and edit the doc.

## Types of documentation

Different types of documentation serve different purposes, and therefore have
different standards and styles.

### Process documentation

Write these in collaboration with the team.

Keep them short and to the point, otherwise nobody will read them.

Lists of **DO** and **DON'T** are good for guideline-type documents.

Examples can be quite helpful

### Design documentation and specifications

Again, something is better than nothing.

Just write it down and commit it to the code repository.

Make the document's status clear. For example, if you are writing a design which
isn't implemented yet, then state this fact at the top of the document.

Where possible, link design documentation to other material such as:
 - Haddock documentation
 - Source code on GitHub
 - User manuals
 - User Stories on Jira

### Code documentation

If it fits in Haddock, then put it in Haddock. Otherwise, link to an external
document.

If you write documentation in plain non-Haddock comment blocks, it will be more
difficult to find in future, so best to avoid this.

### API documentation

Use automatic API documentation systems where appropriate:

- [Haddock](https://www.haskell.org/haddock/doc/html/index.html)
- [Swagger / OpenAPI](https://swagger.io/) for web APIs
- [Typedoc](https://typedoc.org/) for TypeScript

The API documentation should be published to a website by CI process.

### Developer tips and guides

Examples of these are instructions on how to build the code or run tests.

Put these in the Git repo with the code under an appropriate subdirectory. If
the topic is common to all projects, use the
[input-output-hk/adrestia](https://github.com/input-output-hk/adrestia) repo.

### User Manuals

Apply the [Documentation System](https://documentation.divio.com/) model for user
documentation.

Store user documentation in the Git repo with the code.

Use CI (e.g. GitHub actions) to publish user docs from the Git repo to a static
web site.

### User Stories and Requirements

Put these in [[Jira]] as _User Story_ type tickets so that they can be linked to
development tasks.

## Documentation Formats

Prefer Markdown (e.g. [CommonMark][] or [GFM][]) whenever possible. This format
is simple, ubiquitous, and very effective for most purposes.

Sometimes LaTeX may be necessary for your document, but start with Markdown, and
convert to LaTeX only once you're certain that you need it.

[CommonMark]: https://commonmark.org/
[gfm]: https://github.github.com/gfm/

Avoid using proprietary software for writing and publishing documentation. Some
of these systems may look all nice and flashy, but they will usually bite us in
the future.

### Effluence

Please do not use [Effluence](https://input-output.atlassian.net/wiki/home) for
Adrestia documentation. It's horrible.

### Google Docs

Some people find that Google Docs can be helpful for drafting documents. But
once the document is in a reasonably complete state, export it to a Git Repo,
and trash the original, so that people don't accidentally consult the wrong
document.

### GitHub Wiki

The Wiki feature of GitHub would _almost_ be good enough for some of our
purposes, except that the provided formatting options are quite limited. And
GitHub Wiki pages aren't indexed by Google, which is bad for users.

## Review Process

We wish to remove the barriers preventing developers from writing
documentation. We especially want to make it easy for people to update and
improve existing documentation.

Therefore, **PR review is optional for documentation updates**.

You can of course engage other team members to help with drafting and reviewing
of docs, but often this isn't necessary.

The idea is to have Wiki-like ease of publishing, but without the crap Wiki
part.

Documentation mistakes can usually be reversed or corrected later, without
adverse effects. Use your judgement to decide whether or not to request reviews
of a documentation change.

## How to write documentation

Follow the documentation on the [Emanote Website](https://note.ema.srid.ca/) for
information on how to use the publishing system. Following by example is the
easiest way to get something done.

Install `emanote` locally using those instructions, or just use the [[Nix]] shell
contained in this repo.

```shell-session
[~/iohk/adrestia/process]$ nix develop

[nix-shell:~/iohk/adrestia/process]$ emanote
[Info] Launching Ema under: /home/rodney/iohk/adrestia/process
...
[Info] ============================================
[Info] Running live server at http://127.0.0.1:8000
[Info] ============================================
[Info#Ema.Helper.FileSystem] Monitoring /home/rodney/iohk/adp/adrestia/process for changes
[Info#Ema.Helper.FileSystem] Monitoring /nix/store/b7bl4r7hljdy2dk14cxxbpji58x9f5iy-emanote-0.3.12.1-data/share/ghc-8.10.7/x86_64-linux-ghc-8.10.7/emanote-0.3.12.1 for changes

```

### TODO notes

If something is incomplete, add a markdown bulleted list containing an empty
markdown checkbox (`[ ]`), so that we know to come back to it.

- [x] This thing was done.
- [ ] Write more documentation.

These todo items will appear in the [Task Index](/-/tasks).

## Style

- Strive to make your document easy to read. Otherwise people won't read it.

- Write in short and clear sentences.

- Use headings to divide your document into logical sections.

- Apply the _IOHK Style Guide_ where applicable.