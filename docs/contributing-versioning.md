We follow [Semantic Versioning](http://semver.org) a.k.a. "SemVer" for all versioning used across our projects. See the site for full details and reasoning.

In short this means using a version number like `x.y.z` with three scopes:

* `x` is the "major" version. This is incremented when you make a change that is not backwards compatible (you *change* your [API](https://en.wikipedia.org/wiki/Application_programming_interface)).
* `y` is the "minor" version. This means something was *added* but doesn't break anything (you merely *add* to your [API](https://en.wikipedia.org/wiki/Application_programming_interface)).
* `z` is the "patch" version. This simply means bugs were fixed but no functionality was otherwise changed.

This helps makes dependencies more predictable. If you make a new backwards-incompatible version of a popular library you release it with a new major version number so old things that depend on it do not break, assuming they had asked for the specific version they needed. 


## Starting new development
 
When something new is created, say a new module, it starts at a placeholder `0.0.1-SNAPSHOT` version.

The `-SNAPSHOT` means any build made will be of version `0.0.1` yet not count as a release - just an unstable preview. Snapshots can be built over and over.
 
You usually will want to keep working with this number unchanged until you're ready to release something. You have two goals to pick from:

* Stay in the `0.y.z` range. This means you do not consider your module ready for regular use yet, but might like to do informal test releases. You could consider `y` in this case to mean "breaking" and `z` not.
* Go to the `1.y.z` range and make your next published release count as the first playable for the general public. Hooray! But no take-backsies! If you release at `1.0.0` you make a promise to not break anything until `2.0.0`


## Making a release

In either case if you do a formal release without `-SNAPSHOT` that must remain the *only* time that release number is ever used! No recycling or re-releasing with the same number! Numbers are cheap and there are a lot of them.

We aim to use a release process in our [Jenkins](http://jenkins.terasology.org) build server to publish a release that'll automatically take off the `-SNAPSHOT` at release time after asking you what *scope* you're releasing at (major, minor, or patch)

Until that is entirely complete (still experimental) we usually just do the scope increment manually, run a release build, then increment to the next snapshot by adding `0.0.1-SNAPSHOT` to the released version (so next after `1.0.0` is `1.0.1-SNAPSHOT`)

For multiplayer in particular it is critically important that we don't release two modules with the same version number but different content. This can cause all kinds of havoc and obscure issues.


## Specifying a dependency at a given version

The dependencies of a module are specified in the `module.txt` file that can be found in the root directory of a module.

The module.txt is a text file in the json format. The json object in that file can have a field called "dependencies". If it doesn't have one yet look at other files to see how it is done. To define a single dependency to the Core module in 0.54.* you would set the dependencies field to:

```json
    "dependencies" : [
            {
                "id" : "Core",
                "minVersion" : "0.54.0"
            }
    ],
```

If the first major part of the version number is 0 like in the example, then the exclusive maximum version is one minor version higher. Thus the following would also specify a 0.54.* dependency:

```json
    "dependencies" : [
            {
                "id" : "Core",
                "minVersion" : "0.54.0",
                "maxVersion" : "0.55.0"
            }
    ],
```


The above version range includes the version 0.54.0 and 0.54.0-SNAPSHOT and excludes the version  0.55.0 and 0.55.0-SNAPSHOT. Any other 0.54.* version like 0.54.2 is also included.
