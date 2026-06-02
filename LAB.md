# LAB — день 4

Курс: [«Интенсив по погружению в GIT»](https://slurm.io/git-intensive)


## Базовая задача — `01-merge-vs-rebase`

### Стартовое состояние

Было сделано перед началом разрешения конфликтов: ветка `feat/perf-tuning`, 4 файла были изменены webapp/config.py webapp/services.py webapp/templates/index.html Dockerfil; встречный коммит на `main`

```bash
# git log --oneline --graph --all (на момент окончания подготовки)
```

![Шаги до конфликта](screenshots/01-pre-merge-history.png)

### Путь A — через `merge`

В ветке `experiment/merge`, webapp/config.py и webapp/templates/index.html разрешал через VS Code Merge Editor остальные через CLI. 

```bash
# ключевые команды
```

![Состояние Merge Editor / CLI на момент конфликта](screenshots/02-merge-conflict.png)

![Финальный merge-коммит](screenshots/03-merge-result.png)

### Путь B — через `rebase`


```bash
# ключевые команды
```

![История после rebase](screenshots/04-rebase-result.png)

### Сравнение

Финальная история всех веток рядом:

![Сравнение историй experiment/merge vs experiment/rebase](screenshots/05-history-comparison.png)

Что я заметил в процессе сравнения:
- размер истории,
- отсутствие merge-коммита —
- хеши коммитов фичи разные
- невидна в истории ветка как сущность.


### Какой подход я бы выбрал(а) в команде и почему

Свободный ,например: для слияния готовой фичи в общий `main` через PR — `merge` (или `merge --no-ff`); для обновления **своей** приватной ветки от свежего `main` перед PR — `rebase`. Подкрепите свой выбор тем, что увидели в этом задании.

## Задания со звездочкой (опционально)
> это заполняете только если делали. иначе не включайте в отчет и удалите их шаблона

### ⭐1 — `git pull` vs `git pull --rebase`

Что было воспроизведено, какая разница в истории получилась, какую глобальную настройку поставили в `~/.gitconfig`.

![Состояние истории до/после pull --rebase](screenshots/star-1-pull-rebase.png)

### ⭐2 — `--force-with-lease` vs `--force`

--force-with-lease` безопаснее `--force`, не даёт случайно запароть ветку с чужими изменениями.

![Push --force-with-lease успех](screenshots/star-2-force-with-lease.png)

### ⭐3 — rebase с конфликтом на каждом коммите

Сюжет, через сколько `--continue` прошли, что почувствовали по сравнению с пассивным merge.

![Финал rebase --continue](screenshots/star-3-multi-conflict.png)

### ⭐4 — безопасный выход из detached HEAD

Как зашли в detached HEAD, какой коммит сделали, как выходили через `git switch -c`, чем `git reflog` помог как страховка.

![Выход из detached HEAD](screenshots/star-4-detached-head.png)

