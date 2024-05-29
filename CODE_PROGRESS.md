

Commit Workflow
==============

Eventually, I prefer devs to just commit code right to master and then we do all our code review and checks before releasing to production. However, for the initial first bit, please submit a pull request and I will review and merge.

Commit Messages
===============

I'm a little picky when it comes to commit messages. I don't expect you to write a novel, but please be descriptive. If you're fixing a bug, please include the github issue number in the commit message (like #123). If you're adding a feature, please include a brief description of the feature. If you're refactoring, please include a brief description of what you're refactoring.

Please prefix any commits with [XXX] where XXX is the type of stuff you are working on. Usually I follow this notation, but it's not set in stone:

- [gpt] - Specdoctor related work
- [iot] - IoT or sensor related work
- [infra] - Infrastructure related work
- [maps] - Mapping related work / GIS work
- [arcgis] - ArcGIS related work

But feel free to make your own, I just find it helpful to have this be searchable. Examples of good commit messages:

```
[gpt] Fixed bug relating to parsing unicode chars #123
```

Bad commit messages:

```
bug
```


