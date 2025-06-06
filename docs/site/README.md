# OCIO Homepage Development

The OCIO homepage is built with Hugo which you will need to build the static HTML served from the gh-pages branch.

## Building For Development

**Step 1:** Fork or clone the repository, be sure to make a new branch for your changes, follow [OCIO contribution guidelines](https://github.com/AcademySoftwareFoundation/OpenColorIO/blob/main/CONTRIBUTING.md) for branch naming!

```shell
git clone https://github.com/AcademySoftwareFoundation/OpenColorIO.git
```

**Step 2:** Install Hugo.

[Instructions available here!](https://gohugo.io/getting-started/installing)

**Step 3:** Run locally.

Navigate to the homepage folder:

```shell
cd OpenColorIO/docs/site/homepage
```

Run Hugo:

```shell
hugo server --themesDir ../.. http://localhost:1313/
```

**Step 4:** Make changes!

Navigate to http://localhost:1313 in your web browser of choice and see your changes live!

**Step 5:** Submit a PR

Check out the [OCIO guidelines](https://github.com/AcademySoftwareFoundation/OpenColorIO/blob/main/CONTRIBUTING.md) for information about this too!