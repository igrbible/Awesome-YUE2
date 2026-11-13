# Contribution Guidelines

Thank you for helping. This list exists to save people time when they look for anything built on YuE2, so every entry has to earn its place.

## What belongs here

- The project uses, extends, converts, trains, evaluates or explains YuE2 (or the official tools released with it, such as SheetSage2 and MERT2), or a tool that is widely used together with it.
- It is public, it works, and it has enough documentation that a stranger can start with it.
- Its repository is not archived or marked as deprecated, and it has been updated in the last six months.
- Weights name their base model and, where the author gives one, their licence. Adapters sold or presented as the voice of a named real person without that person's consent are not listed.
- Mirrors, re-uploads without changes and empty repositories are not listed.

## How to add an entry

- Open a pull request that adds one entry per pull request, or one pull request for a few closely related entries by the same author.
- Use this format: `- [Name](link) - Description.`
- Put the entry in the section where people would look for it. Official resources come first in their section; everything else is sorted alphabetically by name, ignoring case and punctuation.
- Write the description as one honest sentence about what the project does. Start with a capital letter, end with a full stop, and leave out marketing words, star counts and emoji.
- Link to the project itself (the repository, the model card or the Space), not to a mirror, a shortener or a social media post.
- When two projects share a name, add the owner in parentheses after the name, for example `YuE2 Studio (owner)`.
- If you maintain the project, say so in the pull request.

## Changing or removing an entry

Open an issue or a pull request when a link is dead, a project has been archived, a description is wrong, or an entry no longer meets the rules above. Authors who want their project removed only need to ask.

## Entries by the maintainers

This list is maintained by the authors of Ruach Studio. Our own projects follow the same rules as everyone else's, sit in their alphabetical place, and end their description with a note that we made them. If you think one of them does not belong, open an issue.

## Checks

Every pull request runs [awesome-lint](https://github.com/sindresorhus/awesome-lint) and a link checker. You can run the linter locally with `npx awesome-lint`.
