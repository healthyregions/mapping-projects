# healthyregions.github.io

Web map repository for various projects from the Healthy Regions &amp; Policies Lab.

Individual projects are stored in subdirectories and published to `maps.healthyregions.org/project-name`.

Subdirectories can contain content native to this repo, or can be submodules that link directly to other repositories.

![structure](./structure.png)

Submodules have the benefit of retaining an author's autonomy over the home repository, and also allows for the incorporation of existing projects.

Native subdirectories have the advantage of keeping all code in this repo, and being generally easier to deal with.

Both native subdirectory and submodule repos must have an `index.html` file in their root.

## Publish submodule updates

If changes are made to an external repo that is implemented here as a submodule, a GitHub pages will need to be rebuilt for those changes to be published.

An admin of this repo can trigger the rebuild with the following four clicks:

![running pages workflow](./run-workflow.png)

The changes will be published within a few moments.

## Managing submodules

### Add/remove

In a local clone of the repo

```
git submodule add https://github.com/<user>/<repo> <subdirectory>
git commit
```

```
git rm <subdirectory>
git commit
```

### Maintenance

Note that the pages build process won't actually update submodules in the committed code base. For that, an admin can use something like:

```
git clone https://github.com/healthyregions/healthyregions.github.io --recurse-submodules
cd healthyregions.github.io
git submodule update --recursive --remote
git commit
```

## Analytics

To add basic analytics tracking to your project, put this line somewhere between the `<head>` and `</head>` tags of your `index.html` file:

```
<script defer data-domain="maps.healthyregions.org" src="https://plausible.io/js/script.js"></script>
```
