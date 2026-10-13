Questions

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
