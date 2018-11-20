---
title: Fejlfinding af, hvordan du udvikler en brugerdefineret visualisering i Power BI
description: I denne artikel beskrives nogle almindelige problemer, som kan opstå under udviklingen eller oprettelsen af en brugerdefineret visualisering i Power BI.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 11/06/2018
ms.openlocfilehash: d6f3f654574e9cca081ae2f8191fd7b9fc017afd
ms.sourcegitcommit: 02f918a4f27625b6f4e47473193ebc8219db40e2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/07/2018
ms.locfileid: "51223535"
---
# <a name="troubleshoot-power-bi-custom-visuals"></a>Fejlfind brugerdefinerede visualiseringer i Power BI

## <a name="debug"></a>Fejlfinding

**Pbivi-kommando blev ikke fundet (eller tilsvarende fejl)**

Når du kører `pbiviz` i terminalens kommandolinje, bør du få vist hjælpeskærmen. Hvis det ikke er tilfældet, er den ikke installeret korrekt. Sørg for, at du har mindst 4.0-versionen af NodeJS installeret.

**Hvis du ikke kan finde visualiseringen til fejlfinding på fanen Visualiseringer**

Visual for fejlfinding ligner et prompt-ikon på fanen **Visualiseringer**.

![Valg af visualisering](media/power-bi-custom-visuals-troubleshoot/powerbi-developer-visual-selection.png)

Hvis du ikke kan se det, skal du sørge for, at det er aktiveret i Power BI-indstillingerne.

> [!NOTE]
> Visual for fejlfinding findes kun i Power BI-tjenesten og ikke i Power BI Desktop eller mobilappen. Det pakkede visual fungerer stadig overalt.

**Det var ikke muligt at kontakte serveren med dit visual**

Kør visualiseringsserveren med kommandoen `pbiviz start` i terminalens kommandoline fra roden afvisualiseringsprojektet. Hvis serveren kører, er det sandsynligt, at SSL-certifikaterne ikke er installeret korrekt.

## <a name="next-steps"></a>Næste trin

Du kan finde flere oplysninger og få svar på spørgsmål under [Ofte stillede spørgsmål om brugerdefinerede visualiseringer i Power BI](power-bi-custom-visuals-faq.md#organizational-custom-visuals).