# Contributing to Aurora

Thank you for your interest in Aurora.

Aurora is an independent, actively developed self-hosted multimedia platform. The project is still evolving quickly, so contribution guidelines will become more formal as Aurora approaches its first stable public release.

## Ways to contribute

Useful contributions include:

- reproducible bug reports
- testing
- documentation improvements
- translations
- UI and UX improvements
- frontend development
- backend development
- Linux packaging
- metadata providers and integrations
- platform clients

## Bug reports

A useful bug report should include:

- Aurora version
- operating system and version
- browser or client
- clear reproduction steps
- expected behavior
- actual behavior
- relevant logs
- screenshots when they help explain the problem

Never include passwords, API keys, access tokens, private certificates, database credentials or other secrets in an issue.

## Feature requests

Feature requests should explain the problem or workflow being improved, not only the proposed implementation.

Aurora is designed around a few core principles:

- local-first media
- self-hosting without unnecessary administration
- a polished streaming-style experience
- one coherent environment for multiple types of entertainment

Suggestions that fit those goals are especially useful.

## Development

Aurora currently contains multiple parts, including its frontend, backend, server/installation infrastructure and automated tests.

Before submitting code:

1. Keep changes focused.
2. Avoid committing generated builds, packages, secrets or local configuration.
3. Run the relevant type checks, builds and tests for the area you changed.
4. Document behavior changes when appropriate.
5. Keep user-facing changes consistent with Aurora's existing interface and product direction.

## Pull requests

Pull requests should include:

- a concise description of the change
- why the change is needed
- how it was tested
- screenshots for meaningful UI changes
- any migration, installation or compatibility impact

Large architectural changes should be discussed before substantial implementation work begins.

## Security

Do not open a public issue containing a real credential, private key, exploitable secret or other sensitive information.

If you discover a security issue, avoid publishing sensitive technical details until a private reporting process is available.

## License

Contribution terms will follow Aurora's project license once the repository license has been finalized.
