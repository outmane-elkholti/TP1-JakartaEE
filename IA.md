# Utilisation de l'intelligence artificielle — TP 1

## Introduction

Dans le cadre de la réalisation de ce TP, j'ai utilisé ChatGPT pour m'aider à comprendre certaines notions, résoudre des problèmes d'intégration entre les différentes classes Java et vérifier mon implémentation par rapport aux consignes et au support de cours.

J'ai également utilisé l'IA pour m'accompagner dans les différentes étapes de réalisation et de vérification du projet.

## 1. Création du record LlmInteraction

### Problème rencontré

Je devais créer un record Java permettant de retourner plusieurs informations à partir de la méthode `envoyerRequete()`.

### Raison de l'utilisation de l'IA

J'ai utilisé l'IA pour comprendre le fonctionnement des records Java et déterminer leur syntaxe.

### Prompt utilisé

> explique ce qu'est un record en java et donne moi un exemple

### Réponse de l'IA

L'IA m'a expliqué qu'un record permet de représenter simplement un ensemble de données et génère automatiquement son constructeur et ses méthodes d'accès.

Voici un exemple simple pour illustrer son fonctionnement :

```java
public record Personne(String nom, int age) {
}
```

Pour créer une instance de ce record et accéder à ses données :

```java
Personne personne = new Personne("Ahmed", 22);

System.out.println(personne.nom());
System.out.println(personne.age());
```

### Ce que j'ai appris

J'ai appris qu'un record Java permet d'éviter d'écrire manuellement un constructeur et des méthodes d'accès lorsque l'objectif est simplement de transporter des données.

## 2. Configuration de la variable d'environnement sous Windows

### Problème rencontré

Je devais configurer ma clé API Gemini afin que mon application puisse la récupérer sans l'écrire directement dans le code source.

### Raison de l'utilisation de l'IA

J'ai utilisé l'IA pour savoir comment créer et configurer une variable d'environnement sous Windows.

### Prompt utilisé

> ou est ce que je met le fichier de configuration pour mettre l'api

### Réponse de l'IA

L'IA m'a expliqué qu'il n'était pas nécessaire de créer un fichier de configuration. Il suffisait de créer une variable d'environnement utilisateur sous Windows en suivant les étapes suivantes :

1. Appuyer sur `Windows + R`.
2. Saisir `sysdm.cpl`.
3. Accéder aux paramètres système avancés.
4. Cliquer sur « Variables d'environnement ».
5. Créer une variable utilisateur nommée `GEMINI_KEY` et lui attribuer la valeur de la clé API.

Il fallait ensuite redémarrer IntelliJ IDEA et le serveur Payara pour prendre en compte la nouvelle variable d'environnement.

Pour vérifier que la variable existe, l'IA m'a proposé la commande PowerShell suivante :

```powershell
Test-Path Env:GEMINI_KEY
```

La récupération de la clé dans le code Java se fait avec :

```java
String key = System.getenv("GEMINI_KEY");
```

### Ce que j'ai appris

J'ai appris à créer une variable d'environnement sous Windows et à récupérer sa valeur dans une application Java avec la méthode `System.getenv()`.

J'ai également compris que cette méthode permet de ne pas écrire directement la clé API dans le code source et d'éviter de l'exposer sur GitHub.