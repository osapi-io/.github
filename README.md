<p align="center">
  <picture>
    <source srcset="profile/asset/logo-dark.svg" media="(prefers-color-scheme: dark)">
    <source srcset="profile/asset/logo-light.svg" media="(prefers-color-scheme: light)">
    <img src="profile/asset/logo-dark.svg" alt="osapi-io" width="360">
  </picture>
</p>

<p align="center">The organization profile, and the files every osapi-io repository falls back to.</p>

<p align="center">
  <a href="LICENSE"><img alt="license" src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=for-the-badge"></a>
  <a href="https://conventionalcommits.org"><img alt="conventional commits" src="https://img.shields.io/badge/Conventional%20Commits-1.0.0-yellow.svg?style=for-the-badge"></a>
  <a href="https://github.com/osapi-io"><img alt="organization" src="https://img.shields.io/badge/github.com-osapi--io-blue?style=for-the-badge&logo=github&logoColor=white"></a>
  <img alt="github commit activity" src="https://img.shields.io/github/commit-activity/m/osapi-io/.github?style=for-the-badge">
</p>

<p align="center">
<b>Two jobs: the page people land on, and the files repositories inherit.</b>
</p>

<p align="center">
Nothing here is built or imported. GitHub reads this repository by name and by
path, so where a file sits decides what it does.
</p>

## Usage

`profile/README.md` is rendered at [github.com/osapi-io](https://github.com/osapi-io).
No other file in this repository appears there, and the file has no effect
anywhere else.

Everything at the root is a community health file. GitHub serves one to any
repository in the organization that does not have its own copy. It never
replaces a copy a repository already has, so adding a file here changes nothing
for a repository that carries its own.

That distinction matters for what is actually in use today:

| File | Served to | Also carried by |
| --- | --- | --- |
| [SECURITY.md](SECURITY.md) | all seven repositories | none of them |
| [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) | nothing | all seven |
| [AI_POLICY.md](AI_POLICY.md) | nothing | all seven |
| [LICENSE](LICENSE) | nothing, GitHub has no license fallback | all seven |

So `SECURITY.md` is the only one doing the fallback job. The other three exist
as the organization's canonical copy, which is what the profile page links
rather than picking one repository's copy and implying it speaks for the rest.

`AI_POLICY.md` is not a file GitHub recognizes. It is served to nobody and
inherited by nobody. It is here to be linked.

## Changing the profile page

Edit `profile/README.md`. It takes effect on merge, with no build step and no
deploy. The wordmark beside it is `profile/asset/logo-dark.svg` and its light
counterpart, drawn from the five colours in osapi's logo like every sister
repository's.

Every link in that file is absolute. The page is served from the organization
URL rather than from this repository, so a relative link there is not worth
finding out the hard way.

## License

The [MIT](LICENSE) License.
