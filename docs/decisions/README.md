# Architecture

<script src="https://unpkg.com/mermaid/dist/mermaid.min.js"></script>
<script>
  // Replaces <pre class="mermaid"> blocks with <img> blocks, to make mermaid render properly.
  // Preserves classes and styling so they can be used to fix sizing if necessary.

  mermaid.initialize({ startOnLoad: true });
</script>

## Définitions 
Une décision d'architecture (DA) est un choix de conception d'un logiciel qui répond à une exigence fonctionnelle ou non fonctionnelle importante sur le plan architectural. 

Un enregistrement de décision d'architecture [ADR](httsp://adr.github.io) capture une seule décision architecturale, comme c'est souvent le cas lors de la rédaction de notes personnelles ou de comptes rendus de réunions ; l'ensemble des ADR créés et conservés dans le cadre d'un projet constitue son journal des décisions. 

**Un ADR est immuable** : seul son statut peut changer (c'est-à-dire qu'il peut devenir obsolète ou supplanté). Ainsi, vous pouvez vous familiariser avec l'historique complet du projet en lisant simplement son journal de décisions dans l'ordre chronologique. 

En outre, le maintien de cette documentation vise à : 
- 🚀 Améliorer et accélérer l'intégration d'un nouveau membre de l'équipe 
- 🔭 Éviter l'acceptation/le retour aveugle d'une décision passée  
- 🤝 Formaliser le processus de décision de l'équipe

## Utilisations
Ce site web est automatiquement mis à jour après un changement sur la branche *main* du dépôt Git du projet. Chaque ADR est représenté par markdown.

Le statut d'une ADR peut avoir les états suivants :

<pre class="mermaid">
    flowchart LR;
        A[Brouillon] --> B[Proposée];
        B[Proposée] --> C[Rejetée];
        B[Proposée] --> D[Acceptée];
        D[Acceptée] --> E[Obsolète];
        D[Acceptée] --> F[Remplacée];
</pre>

Proposition de format :
[adr-template-mi](adr-template-mi) contient toutes les sections avec titre en français et les explications associées.

Quelques formats possibles en anglais :

* [adr-template.md](adr-template.md) contient toutes les sections, avec des explications à leur sujet.
* [adr-template-minmal.md](adr-template-minimal.md) ne contient que des sections obligatoires, accompagnées d'explications.. <!-- ### Consequences also contained, though marked as "optional" -->
* [adr-template-bare.md](adr-template-bare.md) toutes les sections sont vides.
* [adr-template-bare-minimal.md](adr-template-bare-minimal.md) comporte les sections obligatoires, sans explications. <!-- ### Consequences also contained, though marked as "optional" -->

La documentation MADR est disponible sur le [site](https://adr.github.io/madr/). .
