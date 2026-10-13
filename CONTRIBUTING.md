# Contribuer

## Workflow

Partir de `main` à jour : `git switch main && git pull`
Créer une branche : `feat/`, `fix/`, `docs/` ou `chore/`
Pousser et ouvrir une PR : `gh pr create --fill --base main`
L'autre relit et approuve (corrections = nouveau commit, pas d'amend)
Fusion en squash : `gh pr merge --squash --delete-branch`

En cas de conflit : rebase sur `origin/main`, puis
`git push --force-with-lease` (jamais `--force`).

## Commits

Format Conventional Commits : `type(portée): description`

Exemple : `feat(api): exposer la version dans X-Visites-Version`

Types : `feat`, `fix`, `docs`, `test`, `refactor`, `chore`

## Tests

    pip install -r requirements.txt
    pytest -q

## pre-commit

    pip install pre-commit
    pre-commit install
    pre-commit run --all-files

hook reformate un fichier : `git add` et recommitter.
