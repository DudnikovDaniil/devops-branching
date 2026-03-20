# devops-branching

Репозиторий для домашнего задания по теме **«Ветвления в Git»**.

## Описание

В этом репозитории отражена работа с ветвлением в Git: создание веток, слияние (merge) и перебазирование (rebase).

## Структура

- `branching/` — каталог с файлами для демонстрации ветвления
  - `merge.sh` — скрипт, работа над которым велась в ветке `git-merge`
  - `rebase.sh` — скрипт, работа над которым велась в ветке `git-rebase`

## Выполненные действия

1. Создан базовый коммит `prepare for merge and rebase`
2. Создана ветка `git-merge` с двумя коммитами:
   - `merge: @ instead *` — замена `$*` на `$@`
   - `merge: use shift` — реализация через `while` и `shift`
3. Внесены изменения в `main` (обновлен `rebase.sh`)
4. Создана ветка `git-rebase` от базового коммита с двумя коммитами:
   - `git-rebase 1` — изменение вывода на "Parameter: $param"
   - `git-rebase 2` — изменение вывода на "Next parameter: $param"
5. Выполнен `merge` ветки `git-merge` в `main` (создан merge-коммит)
6. Выполнен `rebase -i` ветки `git-rebase` на `main` с объединением коммитов через `fixup`
7. Разрешены конфликты при rebase
8. Выполнен `fast-forward merge` ветки `git-rebase` в `main`

## Итоговый граф коммитов

```bash
*   bd0e654 (HEAD -> main) Merge branch 'git-merge'
|\  
| * c1126f3 merge: use shift
| * 1f5d448 merge: @ instead *
* | 9981baa update rebase.sh in main
|/  
* f6650d3 prepare for merge and rebase
```

## Разница между merge и rebase

- **Merge** — создает отдельный коммит слияния, сохраняя историю ветвления
- **Rebase** — переносит коммиты на новую основу, создавая линейную историю

В данном проекте:
- Ветка `git-merge` влита через merge (виден merge-коммит)
- Ветка `git-rebase` влита через rebase + fast-forward (линейная история)

## Ссылки

- [Network граф](https://github.com/DudnikovDaniil/devops-branching/network)
