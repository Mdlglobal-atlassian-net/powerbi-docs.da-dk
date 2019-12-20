---
title: 'DAX: Brug SELECTEDVALUE i stedet for VALUES'
description: Vejledning til, hvornår du skal bruge SELECTEDVALUE-funktionerne.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/20/2019
ms.author: v-pemyer
ms.openlocfilehash: 6aef2c06cc62668ea7dea9fe404e294d1a5faa93
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700472"
---
# <a name="dax-use-selectedvalue-instead-of-values"></a>DAX: Brug SELECTEDVALUE i stedet for VALUES

I din egenskab af dataudformer kan du nogle gange få brug for at skrive et DAX-udtryk, der tester, om en kolonne er filtreret efter en bestemt værdi.

I tidligere versioner af DAX blev dette krav opfyldt på en sikker måde ved hjælp af et mønster, der omfatter tre DAX-funktioner. Funktionerne er [IF](/dax/if-function-dax), [HASONEVALUE](/dax/hasonevalue-function-dax) og [VALUES](/dax/values-function-dax). Der vises et eksempel i følgende målingsdefinition. Momsbeløbet beregnes, men kun for salg til australske kunder.

```dax
Australian Sales Tax =
IF(
    HASONEVALUE(Customer[Country-Region]),
    IF(
        VALUES(Customer[Country-Region]) = "Australia",
        [Sales] * 0.10
    )
)
```

I eksemplet returneres funktionen HASONEVALUE kun TRUE, når en enkelt værdi filtrerer kolonnen **Country-Region**. Når det er sandt, sammenlignes funktionen værdier med konstant teksten "Australien". Når funktionen VALUES returnerer TRUE, multipliceres målingen **Sales** med 0,10 (som repræsenterer 10 %). Hvis funktionen HASONEVALUE returnerer FALSE – fordi mere end én værdi filtrerer kolonnen – returnerer den første IF-funktion BLANK.

Brugen af HASONEVALUE er en defensiv teknik. Den er påkrævet, fordi flere værdier filtrerer kolonnen **Country-Region**. I dette tilfælde returnerer funktionen VALUES en tabel med flere rækker. Når du sammenligner en tabel med flere rækker med en skalaværdi, resulterer det i en fejl.

## <a name="recommendation"></a>Anbefaling

Det anbefales, at du bruger funktionen [SELECTEDVALUE](/dax/selectedvalue-function). Det giver det samme resultat som det mønster, der er beskrevet i denne artikel, men endnu mere effektivt og elegant.

Ved hjælp af funktionen SELECTEDVALUE omskrives eksempelmålingsdefinitionen nu.

```dax
Australian Sales Tax =
IF(
    SELECTEDVALUE(Customer[Country-Region]) = "Australia",
    [Sales] * 0.10
)
```

> [!TIP]
> Det er muligt at overføre en _alternativ resultatværdi_ i funktionen SELECTEDVALUE. Den alternative resultatværdi returneres, når der enten ikke anvendes nogen filtre – eller når der anvendes flere filtre – på kolonnen.

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger om denne artikel i følgende ressourcer:

- [Henvisning til DAX (Data Analysis Expressions)](/dax/)
- Har du spørgsmål? [Prøv at spørge Power BI-community'et](https://community.powerbi.com/)