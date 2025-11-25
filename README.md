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

- [prek](https://github.com/vEnhance/prek) for pre-commit
- [ruff](https://docs.astral.sh/ruff/) for Python formatting and linting
- [pyright](https://microsoft.github.io/pyright/) for type checking
- [djlint](https://djlint.com/) for linting Django templates
- [prettier](https://prettier.io/) for linting CSS, JavaScript, Markdown, JSON, TOML, YAML
- [django-extensions](https://django-extensions.readthedocs.io/) for some extra goodies
- [pytest-django](https://pytest-django.readthedocs.io/en/latest/index.html) for testing

Should be pretty straightforward.

## Setup

Something like the following in an empty Git repository:

```bash
uv init
uv add django django-extensions
uv add --dev copier pytest-django prek pyright
uv run copier copy gh:vEnhance/django-copier-template .
uv run django-admin startproject config .
make install
make migrate
```

Then, add `django_extensions` to `INSTALLED_APPS`.

You should also `uv add --dev pytest-xdist` and `uv add --dev pytest-cov`
if you opted for those testing options.

## Updating

```bash
uv run copier update
```
