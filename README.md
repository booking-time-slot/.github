# booking-time-slot/.github

Центральный репозиторий GitHub Actions для мульти-репо оркестрации.

## Workflow

- `.github/workflows/orchestrator.yml` - единый ручной pipeline:
  - собирает release manifest с SHA сервисов,
  - запускает build/test проверки по `api`, `admin`, `client`, `telegram`,
  - по флагу выполняет deploy через `booking-time-slot-devops/update.sh`.

## Required secrets

- `ORG_CI_TOKEN` - PAT/token с доступом к приватным репозиториям организации.
- `STAGE_HOST` - хост stage сервера.
- `PROD_HOST` - хост production сервера.
- `DEPLOY_USER` - SSH пользователь для деплоя.
- `DEPLOY_SSH_KEY` - приватный SSH ключ для деплоя.

## Recommended repository environments

- `stage`
- `production` (с обязательным manual approval в настройках GitHub Environment)