# Tags

- https://git-scm.com/book/en/v2/Git-Basics-Tagging

View tags

```shell
git tag
```

Create tag

```shell
git tag -a v1.0.0 -m "Release v1.0.0"
git push origin --tags
```

Delete tag

```shell
git tag -d v1.0.0
git push origin --delete v1.0.0
```
