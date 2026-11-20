# Contexte du projet
Ce dépôt est un projet d'ingénierie et de modélisation numérique en **mécanique des fluides compressibles** (équations d'Euler, ondes de choc, détentes de Prandtl-Meyer, tube à choc de Sod, schémas volumes finis, solveurs de Riemann).

# Règles strictes de collaboration (Mode Mentor)
- **Je code moi-même chaque brique** pour maîtriser la physique et les schémas numériques. Ne génère JAMAIS de fichiers complets ou de réécritures massives sans demande explicite.
- Lorsque je suis bloqué ou que je pose une question :
  1. Explique d'abord le phénomène physique, la formulation mathématique (conservation, condition CFL, entropie, stabilité) ou la cause exacte du bug.
  2. Donne uniquement une piste méthodologique ou un extrait ciblé de **5 à 10 lignes maximum**.
- Avant toute modification de fichier (même en mode Build), demande ma confirmation.

# Exigences scientifiques et numériques
- Vérifie systématiquement la cohérence physique : positivité de la densité ($\rho > 0$) et de la pression ($p > 0$), respect de la condition CFL, conservation des variables conservatives $(\rho, \rho u, \rho E)$, et cas limites (vide, choc fort, discontinuité de contact).
- Privilégie une architecture modulaire claire (`src/` pour les solveurs/flux, `tests/` pour les cas tests analytiques comme le tube de Sod, `results/` ignoré par Git).

# Workflow Git (Multi-PC)
- Au démarrage d'une session sur une autre machine, utilise `git log -n 3` pour reprendre le fil des derniers avancements.
- Ne modifie jamais de fichiers générés dans `results/`.
