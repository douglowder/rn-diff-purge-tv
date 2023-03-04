# RN diff PURGE

(This fork is modified to work with the TV repo (https://github.com/react-native-tvos/react-native-tvos) )

This repository exposes an untouched React Native app generated with the CLI
`npx @react-native-community/cli init RnDiffApp`. Each new React Native release causes a new project to be created, removing the old one, and getting a diff between them. This way, the diff is always clean, always in sync with the changes of the init template.

A dedicated branch per release makes changes very easy
to watch. For example:

* https://github.com/react-native-community/rn-diff-purge/compare/release/0.28.0..release/0.29.0
(Change in Android template)
* https://github.com/react-native-community/rn-diff-purge/compare/release/0.29.0..release/0.29.2
(no change)
* https://github.com/react-native-community/rn-diff-purge/compare/release/0.30.0..release/0.31.0
(minor change in `.flowconfig` )
* https://github.com/react-native-community/rn-diff-purge/compare/release/0.30.0..release/0.31.0
(minor change in `.flowconfig` )

See table below for the complete list.

For some more info about the benefits of this repo's way versus the default way and rn-diff's way, read some of the conversation around [here](https://github.com/react-native-community/discussions-and-proposals/issues/68#issuecomment-452227478).

Please :star: this repository if I helped you, and if you upgraded successfully because of `purge`, [buy me a pizza](https://www.buymeacoffee.com/pvinis) :pizza:

## Find the diff you need
https://react-native-community.github.io/upgrade-helper/

## Help us
Help us make [this](https://react-native-community.github.io/rn-diff-purge) full table pretty and more useful.

Probably having some nice alternating row color, having the leftest column stay on top and always visible, and having a nice width for the content of each cell to fit in one line would be some ideas, but you are welcome to try other things!

## Diff table (full table [HERE](https://react-native-community.github.io/rn-diff-purge/))

| From->To | T                                                                                                              | H                                                                                                              | I                                                                                                              | S                                                                                                              |     | I   | S   |     | C   | O   | O   | L   |
| -------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0.60.4-4 | X                                                                                                              | -                                                                                                              | -                                                                                                              | -                                                                                                              | -   |     |     |     |     |     |     |     |
| 0.60.4-3 | [->0.60.4-4](https://github.com/react-native-tvos/rn-diff-purge-tv/compare/release/0.60.4-3..release/0.60.4-4) | X                                                                                                              | -                                                                                                              | -                                                                                                              | -   |     |     |     |     |     |     |     |
| 0.60.4-2 | [->0.60.4-4](https://github.com/react-native-tvos/rn-diff-purge-tv/compare/release/0.60.4-2..release/0.60.4-4) | [->0.60.4-3](https://github.com/react-native-tvos/rn-diff-purge-tv/compare/release/0.60.4-2..release/0.60.4-3) | X                                                                                                              | -                                                                                                              | -   |     |     |     |     |     |     |     |
| 0.60.4-1 | [->0.60.4-4](https://github.com/react-native-tvos/rn-diff-purge-tv/compare/release/0.60.4-1..release/0.60.4-4) | [->0.60.4-3](https://github.com/react-native-tvos/rn-diff-purge-tv/compare/release/0.60.4-1..release/0.60.4-3) | [->0.60.4-2](https://github.com/react-native-tvos/rn-diff-purge-tv/compare/release/0.60.4-1..release/0.60.4-2) | X                                                                                                              | -   |     |     |     |     |     |     |     |
| 0.60.4-0 | [->0.60.4-4](https://github.com/react-native-tvos/rn-diff-purge-tv/compare/release/0.60.4-0..release/0.60.4-4) | [->0.60.4-3](https://github.com/react-native-tvos/rn-diff-purge-tv/compare/release/0.60.4-0..release/0.60.4-3) | [->0.60.4-2](https://github.com/react-native-tvos/rn-diff-purge-tv/compare/release/0.60.4-0..release/0.60.4-2) | [->0.60.4-1](https://github.com/react-native-tvos/rn-diff-purge-tv/compare/release/0.60.4-0..release/0.60.4-1) | X   |     |     |     |     |     |     |     |

## To see the full table containing all releases click [HERE](https://react-native-community.github.io/rn-diff-purge/)

## Notes

### History of this repo

Once upon a time there was react-native. Lots of people used it and loved it. And there were often updates. As many as one per 2 weeks. People loved the new releases with all the new cool APIs and components and bugfixes. But how did they upgrade?

Many people tried to upgrade and automate the process, and many failed. One succeded.

Nicolas Cuillery ([github](https://github.com/ncuillery), [twitter](https://twitter.com/ncuillery)) made a great script and kept it in the [rn-diff](https://github.com/ncuillery/rn-diff) repo. It basically consisted of a `project` branch, which had a react-native project initialized and upgraded using `react-native-git-upgrade`, which he also created. That worked great until it didn't. Nicolas added a few people including me to help with the repo, and we did update it, adding new upgrade diffs. At some point, the upgrades didn't work anymore, the `react-native-git-upgrade` way got too hard to maintain and make work.

I saw that it was easier to just remove the old project and `react-native init` a new one, and then generate the diff. This way I could see the changes in the template as well, helping my projects follow along with the evolution of the RN project templates. That way, an upgrade was never a big undertaking. I forked [rn-diff](https://github.com/ncuillery/rn-diff) and created [rn-diff-purge](https://github.com/react-native-community/rn-diff-purge). The script changed, to remove and recreate the project. This helped me and others by not having to wait for a diff to be generated, they could generate it themselves!

Lastly, the [rn-diff-purge](https://github.com/react-native-community/rn-diff-purge) repo got transfered to the react-native-community organization, in the repo with the same name, [rn-diff-purge](https://github.com/react-native-community/rn-diff-purge). Since then I have made the new way to generate and keep track of releases, made a table that allows for releases to always be diff-able no matter the order. I have kept the [old master](https://github.com/react-native-community/rn-diff-purge/tree/old/master) branch and [old project](https://github.com/react-native-community/rn-diff-purge/tree/old/project) branch for maintaining history, but I have created the new [master](https://github.com/react-native-community/rn-diff-purge/tree/master) branch and the [app-base](https://github.com/react-native-community/rn-diff-purge/tree/app-base) that all releases branch off from, and each release gets its own branch, for example [release/0.58.6](https://github.com/react-native-community/rn-diff-purge/tree/release/0.58.6). We are already working with [react-native-cli](https://github.com/react-native-community/react-native-cli) to help people upgrade as easily as possible, and we will continue to do our best.

Many thanks to you for using this repo, many thanks to Nicolas for starting this, and many thanks to the React Native Core team and React Native Contributors team for helping make this repo and RN project upgrading awesome.

## Why this repository?
`react-native-git-upgrade` is painful. A simple diff by recreating the project is a much much simpler way to get a diff on every new React Native release.

## FAQ

### Why starting from 0.22.0?

Because I couldn't run `react-native init` with an older version than that without the cli throwing errors. I hope people are not using still 0.22.0 anymore (Jan 2019).

### How did you do this?

I made a [script](https://github.com/react-native-community/rn-diff-purge/blob/master/new-release.sh). Then I ran a [helper script](https://github.com/react-native-community/rn-diff-purge/blob/master/new-release.sh) to make the rest of the versions.
Now I just ran the `new-release.sh` script manually when I get the email that there is a new release published on npm, and I am making a bot to do that for me.

### How can I contribute?

Unfortunately it's a bit weird. The `master` branch is the keeping-track one. Then there is the `app-base` branch that is the starting point of every other branch. Every react-native release gets its own branch. So having PRs that change master is great, but for adding a new release, a new branch has to be created, and that is only possible by the contributors of this repo.

Nevertheless, when a new release of React Native is released, we'll have to be prompt to provide
the new diff. Having more collaborators on this project will help in the future. If you're interested, please open an issue to discuss.

One thing that could get some love is the `docs/index.html` file, which produces a very basic html table. I would like to make it prettier and easier to navigation, but my css-fu is level 0. I would love to see what you can do to make it so! <3

### Down here!

If you have:
- questions
- suggestions
- ideas to make this even better
- the urge to just to say hello to me :)

feel free to make an issue or contact me. I'm pretty easy to find!
