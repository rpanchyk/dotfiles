# Remove sensitive text from git history

- https://rtyley.github.io/bfg-repo-cleaner/
- https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository

Create `passwords.txt` file. Replacements are separated by `==>`. If absent - entire string will be removed.

```text
secret_text==>fill_text
```

Remove

```shell
java -jar "C:\Data\Dev\tools\bfg-repo-cleaner\bfg-1.14.0.jar" --replace-text passwords.txt
```

Clean

```shell
git reflog expire --expire=now --all && git gc --prune=now --aggressive
```
