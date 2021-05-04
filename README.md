# Django makemigrations pre-commit hook

Checks whether there are any changes to migrate in Django.

## Usage

This repository contains two hooks:

1. Check (`manage.py makemigrations --check`)
2. Dry-run (`manage.py makemigrations --dry-run`)

You should specify which hook to use in your pre-commit configuration.

### Check

The check hook will return an error code if there are any changes to migrate,
preventing the deveplers to commit unless migrations for all changes are present
in the commit.

```yaml
repos:
- repo: https://github.com/potasiak/pre-commit-django-makemigrations
  rev: main
  hooks:
  - id: django-makemigrations-check
```

### Dry-run

The dry-run hook will not return an error code even when there are changes to
migrate but will still display the changes that have to be migrated. It won't
stop the developers from commiting without migrations for all changes.

```yaml
repos:
- repo: https://github.com/potasiak/pre-commit-django-makemigrations
  rev: main
  hooks:
  - id: django-makemigrations-dry-run
```
