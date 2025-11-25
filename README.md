# django-copier-template

This is a Django copier template used by Evan Chen for the following projects:

- [OTIS-WEB](https://github.com/vEnhance/otis-web)
- [apply.evanchen.cc](https://apply.evanchen.cc)
- [AtheWeb](https://github.com/vEnhance/athe-web)

Turns out the configuration files are all basically identical
and I don't want to keep copying them back and forth.

## Synopsis

This is used to set up a [Django](https://www.djangoproject.com/)
project using [uv](https://docs.astral.sh/uv/).
It uses the following frameworks:

- prek for pre-commit
- ruff
- pyright for type checking
- djlint for linting Django templates
- prettier for linting CSS, JavaScript, Markdown, JSON, TOML, YAML
- django-extensions for some extra goodies
- [pytest-django](https://pytest-django.readthedocs.io/en/latest/index.html) for testing

Should be pretty straightforward.

## Setup

Something like the following:

```bash
uv init
uv add django django-extensions
uv add --dev copier pytest-django
uv run copier gh:vEnhance/django-copier-template .
uv run django-admin startproject CONFIG_NAME
```

## Updating

```bash
uv run copier update
```
