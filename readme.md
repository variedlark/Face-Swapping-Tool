# MASQUE STYLISÉ VIA RA + CHEVEUX

Filtre AR en temps réel (webcam) : il applique
1) un **masque stylisé** (PNG RGBA) sur le visage, et  
2) une **perruque** (cheveux extraits automatiquement depuis ce masque).

> **Aucun visage/masque n’est fourni par défaut** dans ce dépôt.  
> Chaque utilisateur ajoute son propre `assets/mask.png`.

---

## Fonctionnalités
- **Face tracking** via *MediaPipe Face Landmarker* (landmarks + tracking temps réel pour effets/avatars) [1].
- **Segmentation cheveux** via *MediaPipe Image Segmenter* (modèle multiclasses) avec **confidence mask** pour des bords plus naturels [2].
- **Extraction automatique des cheveux** depuis `assets/mask.png` → génère `assets/wig.png` et `assets/wig_src_points.npy`.
- Optimisations : stabilité améliorée (filtrage), bords adoucis, latence réduite (pipeline asynchrone).

---

## Prérequis
- Python **3.9+** recommandé.
- Git installé (VS Code utilise le Git **de la machine** pour Source Control) [3].
- macOS / Windows / Linux.

---

## Installation (local)

### 1) Cloner
```bash
git clone https://github.com/variedlark/Face-Swapping-Tool.git
cd <Face-Swapping-Tool>
```

### 2) Créer et activer un venv
```bash
python3 -m venv .venv
source .venv/bin/activate
```


### 3) Installer les dépendances

```bash
pip install -r requirements.txt
```

### 4) Télécharger les modèles (non versionnés)

Les modèles ne sont pas inclus dans le repo (taille/licence). Télécharge-les avec :

```bash
./scripts/download_models.sh
```

***

## Ajouter ton masque (obligatoire)

### 1) Ajoute ton fichier

Place ton PNG RGBA ici :

    assets/mask.png

Ton `mask.png` doit être en **RGBA**.

### 2) Générer la perruque (cheveux) depuis le masque

```bash
python3 prepare_wig.py
```

Ça génère localement :

*   `assets/wig.png`
*   `assets/wig_src_points.npy`

***

## Lancer

```bash
python3 run_filter.py --mirror
```

Options utiles :

*   `--camera N` : sélectionner une autre webcam
*   `--debug` : afficher des points/repères de debug

***

## Structure du projet

    .
    ├── ar_filter/
    │   ├── __init__.py
    │   ├── overlay.py
    │   ├── tracker.py
    │   ├── warp.py
    │   └── hair_segmenter.py
    ├── assets/
    │   ├── .gitkeep
    │   └── (fichiers ajoutés localement par l’utilisateur)
    ├── scripts/
    │   └── download_models.sh
    ├── prepare_wig.py
    ├── run_filter.py
    ├── requirements.txt
    └── README.md

***

## Politique de fichiers (important)

Ce dépôt **n’inclut pas** (volontairement) :

*   `assets/mask.png` (contenu utilisateur)
*   `assets/wig.png`, `assets/wig_src_points.npy` (générés localement)
*   `assets/*.task`, `assets/*.tflite` (modèles ML)

Ces fichiers sont ignorés via `.gitignore`.

***

## Dépannage

### VS Code ne propose pas les actions Git

VS Code dépend de l’installation Git du système (Git 2.0+). Installe Git puis relance VS Code \[3].

### “Je ne vois pas `assets/` sur GitHub”

Normal si le dossier est vide : Git ne track pas les dossiers vides. Assure-toi que `assets/.gitkeep` est bien committé \[4].

### “.gitignore n’ignore pas un fichier”

`.gitignore` ne s’applique qu’aux fichiers **non trackés**. Si un fichier a déjà été committé, il faut le retirer du suivi (`git rm --cached`) puis commit/push \[5].

***

## Workflow Git (push)

```bash
git status
git add -A
git commit -m "Ton message"
git push
```

***

## Licence

Ajoute une licence (MIT / Apache‑2.0 recommandé) avant diffusion large.

***

## Références

\[1] MediaPipe Face Landmarker (Python) — usage pour filtres/avatars, landmarks, temps réel  
<https://ai.google.dev/edge/mediapipe/solutions/vision/face_landmarker/python>

\[2] MediaPipe Image Segmenter — masques `category_mask` / `confidence_masks` pour effets visuels  
<https://ai.google.dev/edge/mediapipe/solutions/vision/image_segmenter>

\[3] VS Code Source Control — prérequis : VS Code utilise le Git installé sur la machine  
<https://code.visualstudio.com/docs/sourcecontrol/overview>

\[4] Git et dossiers vides — utiliser un fichier placeholder `.gitkeep` / `.gitignore` pour conserver un dossier vide  
<https://stackoverflow.com/questions/115983/how-do-i-add-an-empty-directory-to-a-git-repository>

\[5] `.gitignore` et fichiers déjà trackés — retirer du cache avec `git rm --cached`  
<https://stackoverflow.com/questions/45400361/why-is-gitignore-not-ignoring-my-files>

```
```
