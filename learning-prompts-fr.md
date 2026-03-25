# Prompts et guide d'apprentissage IA en pédagogie inversée

Voici une série de prompts et un guide pas à pas pour vous aider à mener une session d'apprentissage augmentée par l'IA, en pédagogie inversée, sur le sujet de votre choix. Les prompts sont conçus pour vous guider dans la construction d'une base de connaissances, l'auto-évaluation de votre niveau, puis un apprentissage socratique avec un LLM comme enseignant.

**Temps estimé :**
- Construction de la base de connaissances : entre 0 et 2 heures. Quasi instantané si vous avez déjà le contenu à étudier. Plus long si vous devez rechercher et télécharger beaucoup de contenu.
- Principaux enseignements et surprises : 10 minutes
- Auto-évaluation : 1 heure
- Apprentissage socratique : 1 à 2 heures
- **Total:** entre 15 minutes et 5 heures, selon la quantité de contenu que vous avez et la profondeur que vous souhaitez atteindre.

## Point de départ

### Objectif d'apprentissage (version initiale)

Formulez une idée générale de ce que vous voulez apprendre et pourquoi. C'est votre objectif d'apprentissage.

### Contexte sur vous

Rédigez une brève description de votre profil. Donnez juste assez de contexte pour aider l'IA à concevoir une meilleure expérience d'apprentissage.

### Premier prompt

```md
Je veux que tu m'aides à étudier le sujet suivant : "<objectif d'apprentissage initial>". Voici un peu de contexte sur moi : <description de toi>.

Garde ces informations en tête et attends mes prochaines instructions.
```

## Construire votre base de connaissances

Vous procéderez différemment selon que vous savez déjà précisément quoi étudier ou non.

### Option : vous voulez trouver du contenu à étudier

Prompt :

```md
Prends un moment pour rechercher des ressources pertinentes pour étudier mon objectif d'apprentissage. Cherche des pages de blog techniques récentes, des vidéos, des articles de recherche et des livres. Évite le contenu marketing d'entreprise. Donne-moi une liste d'environ 10 éléments : titre, mini-résumé, lien.
```

Passez la liste en revue et, si besoin, corrigez :

```md
Refais le même type de recherche, mais ne te limite pas à <a, b, c...> ni aux pratiques associées. Garde les mêmes contraintes que la recherche précédente, mais avec un thème plus général : <sujet affiné>
```

Si la liste devient longue et difficile à suivre :

```md
Classe toutes ces références par type : page web texte, article de recherche texte, vidéo, livre.
```

Vérifiez que tout est accessible :

```md
Passe en revue chaque élément et vérifie que tu peux accéder au contenu. Signale ce qui manque ci-dessous pour que je puisse te le fournir (transcriptions vidéo, articles de recherche, transcriptions de podcasts, livres, etc.).
```

Si nécessaire, faites les téléchargements et uploads manuellement, ou retirez une référence si elle est inaccessible (ou hallucinée).

💡 **Outils utiles pour récupérer du contenu :**
- [TubeTranscript](https://tubetranscript.org/) pour télécharger les transcriptions de vidéos YouTube. Il existe d'autres outils similaires, et Gemini accède aussi directement aux transcriptions YouTube.
- [repomix](https://repomix.com/) pour exporter un dépôt GitHub dans un fichier unique lisible par un LLM.
- [webmix](https://github.com/philou/webmix), un petit outil que j'ai créé pour empaqueter un site web dans un fichier unique lisible par un LLM.
- [Kindle-AI-Export](https://github.com/transitive-bullshit/kindle-ai-export) un outil OCR pour générer des PDF à partir de livres Kindle

Il peut être utile de vérifier la taille du contexte :

```md
Comment toute cette base de connaissances s'insère-t-elle dans ta fenêtre de contexte ?
```

Si ça ne tient pas, vous avez plusieurs stratégies :
- prioriser et retirer certains éléments
- découper l'apprentissage en sous-thèmes

### Option : vous avez déjà du contenu que vous voulez absolument étudier

Par exemple, vous avez peut-être déjà des livres ou des favoris en tête. Vous aurez besoin d'une version PDF sans DRM.

Commencez par vérifier la fenêtre de contexte :

```md
Je prévois d'ajouter <a, b, c> à la base de connaissances. Penses-tu que cela tiendra dans ta fenêtre de contexte ?
```

Même logique que ci-dessus : éventuellement découper par sous-thèmes ou prioriser/retirer des éléments.

Puis ajoutez le contenu :

```md
Ajoute ces éléments à la base de connaissances :

- url
- livre
- ...

Et intègre-les au reste du contenu.
```

### 💡 Privilégier des sources variées

D'après mon expérience, l'apprentissage est de meilleure qualité quand on dispose d'une bonne diversité de sources au lieu de se limiter, par exemple, à un seul livre.

### La base de connaissances est prête

Indiquez au LLM que la base est prête.

```md
La base de connaissances est prête, attends mes prochaines instructions.
```

### Affiner votre objectif d'apprentissage

Vous avez peut-être maintenant une meilleure vision de votre objectif. Vous avez peut-être aussi des sous-objectifs à approfondir. Prenez une minute pour tout noter.

## Option : commencer l'exploration

Si vous voulez obtenir 80 % de la valeur en 20 % du temps, utilisez ce prompt :

```md
Avant de commencer, parcours tout le contenu. Ensuite, à partir de toute cette base de connaissances (contenu en ligne + contenu importé), donne-moi les 5 principaux enseignements et les 5 principales surprises liés à mon objectif d'apprentissage : <objectif d'apprentissage affiné>
```

💡 C'est un bon moment pour commencer à prendre des notes.

💡 Vous pouvez aussi affiner à nouveau votre objectif d'apprentissage en vous basant sur les enseignements et surprises identifiés.

## Auto-évaluation

```md
Voici comment nous allons procéder.

Je veux explorer <objectif d'apprentissage affiné>.

Mes objectifs principaux pour cette exploration sont :
- <insérer vos sous-objectifs ici>
- ...

Je veux apprendre avec une pédagogie inversée, dans le style de "Training from the Back of the Room", où tu joueras le rôle de mon enseignant socratique. Pendant le processus, je prendrai des notes dans mon système de prise de notes. <Si tu prévois d'autres activités d'apprentissage plus tard, indique-le aussi. Ex. : je prévois de lire le livre xxx de toute façon>

Tu baseras ton enseignement sur tout le contenu que nous avons rassemblé : contenu en ligne + contenu importé.

Ta première tâche, dans ce rôle socratique, sera de me faire passer une évaluation de mes connaissances :
- garde en tête que je n'ai pas encore étudié ce contenu
- tu évalueras mes réponses avec le Perfection Game
- tu poseras les questions une par une
- prends le temps de trouver 10 très bonnes questions, transversales, capables d'évaluer mes connaissances sur plusieurs sujets à la fois
- les questions doivent rester simples et pouvoir être répondues en 4 à 5 lignes maximum
- tu utiliseras ensuite cette évaluation pour construire la suite de l'enseignement socratique
- une fois les 10 questions répondues avec feedback, attends mes prochaines instructions

Commence par la première question.
```

Laissez-vous guider. Si vous remarquez que le LLM sort de son rôle d'enseignant socratique, rappelez-lui de rester dans le cadre. Prenez des notes au fur et à mesure.

Après la dixième question :

```md
Donne-moi une synthèse de mon niveau actuel, avec mes points forts, mes lacunes et mes opportunités de progression.
```

Relisez cette synthèse et ajustez vos objectifs d'apprentissage détaillés.

## Apprentissage socratique

Lancez l'apprentissage socratique. En tenant compte de vos lacunes et opportunités, vous devriez maintenant avoir des priorités d'apprentissage détaillées.

```md
Voici d'abord mes priorités d'apprentissage, par ordre décroissant :
1. <insérer les vôtres>

Je suis moins intéressé par les éléments suivants. Je les verrai peut-être plus tard, mais s'il y a quelque chose d'important pour la suite, n'hésite pas à le signaler :
- <insérer les vôtres>

Voici mon objectif global : <objectif final d'apprentissage>

Pour construire mon parcours d'apprentissage socratique, je veux que tu utilises le modèle des 4C issu de "Training from the Back of the Room", afin d'être mon enseignant socratique et de me guider dans la découverte de ces pratiques et de cette théorie.

Peux-tu construire un parcours d'apprentissage unique pour étudier mes <n> principaux sujets d'intérêt ?

Ce parcours doit respecter ce format :
Session 1 : ...
- 4C connexion
- Concept
- Pratique concrète
- Conclusion
Session 2 : ...
- 4C connexion
- Concept
- Pratique concrète
- Conclusion

Et ainsi de suite. Tu peux créer autant de sessions que nécessaire. Chaque session doit prendre entre 10 et 20 minutes.
```

Vérifiez le parcours d'apprentissage et, si besoin, demandez des adaptations :

```md
Commence par la Session 1, étape Connexion :

Rappelle-toi que je veux que tu sois mon enseignant socratique interactif. Quand je dis "commence la session 1", cela signifie "commence par l'étape Connexion". Pose-moi la question ou l'activité prévue dans session1-connexion, puis attends ma réponse. Donne-moi un feedback (Perfection Game à nouveau), puis passe à l'étape Concepts...
```

Laissez-vous guider par l'enseignant socratique. Prenez des notes au fur et à mesure.

### Continuer l'apprentissage

Lorsque vous arrivez à la fin du parcours, plusieurs options s'ouvrent à vous :

- Étendre le parcours avec de nouvelles sessions
- Faire de la pratique délibérée sur les sujets les plus difficiles
- Discuter librement avec l'enseignant socratique pour approfondir et créer de nouvelles connexions

## ⚠️ Points d'attention

- Si l'enseignant socratique va trop vite, saute des étapes, ou part hors-piste : demandez-lui de revenir au plan d'apprentissage.

- L'enseignant socratique peut vous demander : "What would you do|say|code in...". Ne répondez pas directement, le LLM peut se mélanger et interpréter vos mots comme un nouveau prompt. Ajoutez plutôt du contexte dans votre réponse, par exemple :

```md
Voici ce que je dirais :

> ...
```

## Option : Flashcards

À chaque étape terminée, vous pouvez lui demander de générer des flashcards. Exemple de prompt pour Anki :

```md
J'utilise Anki, et je veux que tu génères un CSV avec des questions sur ce que j'ai appris jusqu'ici.
```

Puis plus tard :

```md
Génère-moi un CSV Anki avec des questions sur tout ce que j'ai appris depuis la dernière génération Anki.
```

💡 Préférence personnelle : notre mémoire est limitée. Je garde les flashcards pour ce que je dois retenir "sur le moment". Pour le reste, je m'appuie sur un bon index dans mes notes.

## Prise de notes 101

J'utilise le système de prise de notes de Cornell avec des cartes mentales :

1. Je dessine des cartes mentales pendant l'apprentissage
2. À la fin, je surligne les idées les plus importantes dans la carte mentale
3. J'écris une synthèse de l'apprentissage en quelques puces

💡 Les LLM arrivent de mieux en mieux à extraire les apprentissages clés à partir d'une image de carte mentale. Je préfère cependant faire la synthèse moi-même pour consolider mes connaissances.