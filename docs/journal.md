Questions

TP01:

1: Le delai de changement est de 19h15 car mon camarade ne pouvait pas approuver la PR
2: Marcherait comme GitLab, Gitea ou Forgejo :

- Toutes les commandes git
- La signature SSH des commits et du tag, et sa vérification locale (stockée dans le commit)
- pre-commit et ruff, qui tournent en local
- Les conventions de commits, CONTRIBUTING.md, README.md, docs/
- L'application, les tests (pytest) et Redis en conteneur

Changerait :

- Les commandes gh (glab sur GitLab, tea ou l'interface web sur Gitea/Forgejo)
- Les pull requests (appelées « merge requests » sur GitLab), les revues et la fusion par squash
- La création depuis un modèle, les collaborateurs, les clés SSH du compte et le badge « Verified »
- Les règles de protection de branche

3: La forge sait qui pousse, mais pas qui a écrit le commit : le nom et l'e-mail
d'un commit peuvent être falsifiés. Si quelqu'un pousse un clone contenant les commits
d'un autre, ou si le dépôt est migré vers une autre forge, cette information est perdue.

La signature est enregistrée dans le commit lui-même : elle prouve qui en est l'auteur,
partout et pour toujours, quelle que soit la forge.

TP02:
Secret:

<img width="644" height="404" alt="image" src="https://github.com/user-attachments/assets/43ffe1a2-08f2-4f75-89f2-cead9c8ba18e" />

Comme on peut le voir sur ce screen après exécution de Gitleaks, on ne trouve pas le secret, le jeton n'est pas présent.


1 : Humaines : revue et CODEOWNERS. Automatiques : gitleaks en pre-commit et contrôle gitleaks sur la PR. Gitleaks est plus fiable, car il vérifie chaque commit de façon obligatoire, sans oublier d'étape.

2 : Non : le hook est local et peut être contourné . Gitleaks doit tourner dans le pipeline, en contrôle requis, pour que la règle soit vraiment appliquée.

3 : Non : un secret poussé sur un dépôt public n'est pas privé. Des robots peuvent le trouver très vite, en quelques minutes.
