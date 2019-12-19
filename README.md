# Truffle Box Registry v2 PoC

This is a proof-of-concept to explore a better unboxing system for Truffle projects.

The primary pain-point we are experiencing is that every time someone wants to submit a new box, they have too manually email us. Rather, this should be a PR that simplifies and makes the whole process more transparent and easier to manage as well.

# Prior art: Brunch's skeleton system

*Here's a quick summary:*

1. Have a repo that hosts a `skeletons.json` file listing out each skeleton (see below).
2. On unboxing, look up `skeletons.json`, and simply run `exec("git clone " + url)`
3. Generate a frontend by reading from `skeletons.json`

*Example `skeletons.json` entry:*

```
{
    "title": "React",
    "url": "brunch/with-react",
    "technologies": "Babel, ES6, React",
    "description": "Modern skeleton with React library.",
    "alias": "react"
}
```

*Note*

- we can add tags to the JSON entries (e.g. "official", "community", "partner", etc.)
- people add new skeletons by making a simple PR to the `skeleton.json` file
- the `alias` entry allows people to unpack "react" rather than typing the entire github "path" (i.e. `brunch/with-react`).

*Aside*

Their unboxing logic does much more, but we prob don't want to implement all that in one go. A simple `git clone` should be good enough for now.

*References*

- Brunch Skeletons repo: https://github.com/brunch/skeletons
- Brunch "unboxing" logic: https://github.com/brunch/init-skeleton
