# Overview
Nothing makes a website seem more defunct than a bunch of dead links. That said, when you are moving fast, it can be a headache to keep on top of changes, and downright impossible to stay on top of links to external sites that end up restructuring. There are already great tools out there to solve this problem, and this uses one of them ([linkchecker](https://github.com/linkchecker/linkchecker)) to run checks via GH actions in a simple and easy to customize way.

# Usage
To use the link checker, simply call the action with the domain you want to check. Checkout [this](https://github.com/DAKLabb/gh-actions/blob/main/.github/workflows/link-checking.yaml) example usage in [my repo documenting GitHub Actions](https://github.com/DAKLabb/gh-actions).

```yaml
 - name: Check Links
   uses: DAKLabb/check-links@main
   with:
     url: my URL.
```

## Inputs
| Input            | Required | Description                                                       |
|------------------|----------|-------------------------------------------------------------------|
| url              | X        | The url of the site to check                                      |
| site-name        |          | The name of the site being checked                                |
| report-name      |          | The name of the report as displayed in GitHub                     |
| check-external   |          | Whether to [check extenral](https://linkchecker.github.io/linkchecker/man/linkchecker.html#cmdoption-check-extern) links |
| include-warnings |          | Whether to [include warnings](https://linkchecker.github.io/linkchecker/man/linkchecker.html#cmdoption-no-warnings) |
| debug-config     |          | Logs out the contents of the [linkchecker config](https://linkchecker.github.io/linkchecker/man/linkcheckerrc.html) for verification. |

## Ouputs
If the checker finds bad links, a report will be uploaded as an artifcat to the GH action run. Additionally, the details of the bad links should show up as errors from the run.