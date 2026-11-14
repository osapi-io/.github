<p align="center">
  <picture>
    <source srcset="profile/asset/logo-dark.svg" media="(prefers-color-scheme: dark)">
    <source srcset="profile/asset/logo-light.svg" media="(prefers-color-scheme: light)">
    <img src="profile/asset/logo-dark.svg" alt="osapi-io" width="360">
  </picture>
</p>

<p align="center">The profile page of the organization, and the default files for every osapi-io repository.</p>

<p align="center">
  <a href="LICENSE"><img alt="license" src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=for-the-badge"></a>
  <a href="https://conventionalcommits.org"><img alt="conventional commits" src="https://img.shields.io/badge/Conventional%20Commits-1.0.0-yellow.svg?style=for-the-badge"></a>
  <a href="https://github.com/osapi-io"><img alt="organization" src="https://img.shields.io/badge/github.com-osapi--io-blue?style=for-the-badge&logo=github&logoColor=white"></a>
  <img alt="github commit activity" src="https://img.shields.io/github/commit-activity/m/osapi-io/.github?style=for-the-badge">
</p>

<p align="center">
<b>This repository holds the profile page of the organization and the default files for the other repositories.</b>
</p>

<p align="center">
No build uses this repository. No code imports it. GitHub finds this
repository by its name and finds each file by its path. The path of a file
decides what GitHub does with it.
</p>

## Usage

GitHub shows `profile/README.md` at [github.com/osapi-io](https://github.com/osapi-io).
No other file in this repository shows there. The file has no effect in a
different location.

Each file at the root is a default file. GitHub calls it a community health
file. GitHub serves the file to each repository in the organization that does
not have its own copy. GitHub never replaces the copy that a repository has.
Thus a new file here changes nothing for a repository that has its own copy.

The table shows which files GitHub serves now:

| File | Served to | Has its own copy |
| --- | --- | --- |
| [SECURITY.md](SECURITY.md) | all eight repositories | none of them |
| [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) | nothing | all eight |
| [AI_POLICY.md](AI_POLICY.md) | nothing | all eight |
| [LICENSE](LICENSE) | nothing, GitHub has no default license file | all eight |

Thus GitHub serves only `SECURITY.md` as a default file. The other three files
are the official copies for the organization. The profile page links to these
copies. It does not link to the copy in one repository, because that copy
does not apply to the other repositories.

GitHub does not recognize `AI_POLICY.md`. GitHub serves it to no repository.
It is here only as the target of links.

## Change the profile page

1. Edit `profile/README.md`.
1. Merge the change.

   Note: the change shows on the profile page after the merge. There is no
   build and no deployment.

The wordmark is `profile/asset/logo-dark.svg` and `profile/asset/logo-light.svg`.
Both use the five colours of the osapi logo, as the other repositories do.

Use only absolute links in `profile/README.md`. GitHub shows the page at the
organization URL, not in this repository. Thus a relative link in the page
does not go to the correct location.

## License

The [MIT](LICENSE) License.
