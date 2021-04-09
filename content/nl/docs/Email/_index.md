---
title: "Email"   
linkTitle: "Email"   
weight: 2   
description: Over het gebruik van email binnen onze gemeente.
---

Iedere gebruiker krijgt een **persoonlijk** account, met bijbehorende persoonlijke mailbox.    
Daarnaast zijn er **gedeelde postvakken voor ambten/functies en commissies** binnen onze gemeente.    
Op de speciale pagina over [gedeeld postvak](./gedeeldpostvak) is meer informatie te vinden.

```mermaid
graph BT
     id1([Gebruikersaccount])
     id2(Persoonlijke mailbox)
     id3(Gedeeld postvak)
     id1 --> id2
     id1 -- optioneel -.-> id3
     
     subgraph email [Email / Outlook]
        id2
        id3
     end
    
```