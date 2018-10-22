---
title: Kransediagrammer i Power BI
description: Kransediagrammer i Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: ab292964bb1b6b1f4218d41c46eb2c28c82a034c
ms.sourcegitcommit: ce8332a71d4d205a1f005b703da4a390d79c98b6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/27/2018
ms.locfileid: "47416745"
---
# <a name="doughnut-charts-in-power-bi"></a>Kransediagrammer i Power BI
Et kransediagram ligner meget et cirkeldiagram og viser relationen mellem dele af en helhed. Den eneste forskel er, at centreret i det er tomt og giver plads til en etiket eller et ikon.

## <a name="create-a-doughnut-chart"></a>Opret et kransediagram
I denne vejledning benyttes eksemplet Retail Analysis Sample (Eksempel på detailhandelsanalyse)til at oprette et kransediagram, der viser dette års salg efter kategori. Du skal [downloade eksemplet](../sample-datasets.md) til Power BI-tjenesten eller Power BI Desktop for at følge med.

1. Start på en [tom rapportside](../power-bi-report-add-page.md). Hvis du bruger Power BI-tjenesten, skal du åbne rapporten i [Redigeringsvisning](../service-interact-with-a-report-in-editing-view.md).

2. I ruden Felter skal du vælge **Sales** \> **Last Year Sales**.  
   
3. Vælg ikonet for kransediagram ![ikon for kransediagram](media/power-bi-visualization-doughnut-charts/power-bi-icon.png) i ruden Visualiseringer for at konvertere dit liggende søjlediagram til et kransediagram. Hvis **Last Year Sales** ikke findes i området **Værdier**, skal du trække det derhen.
     
   ![Visualiseringsrude med kransediagram valgt](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. Vælg **Element** \> **Kategori** for at føje det til området **Forklaring**. 
     
    ![kransediagram ud for ruden Felter](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. Du kan eventuelt [tilpasse størrelsen og farven på diagrammets tekst](power-bi-visualization-customize-title-background-and-legend.md). 

## <a name="considerations-and-troubleshooting"></a>Overvejelser og fejlfinding
* Summen af kransediagrammets værdier skal give 100 %.
* Er der for mange kategorier, er det svært at læse og fortolke diagrammet.
* Kransediagrammer er bedst egnet til at sammenligne en bestemt del med helheden og ikke sammenligne de enkelte dele med hinanden. 

## <a name="next-steps"></a>Næste trin
[Tragtformede diagrammer i Power BI](power-bi-visualization-funnel-charts.md)

[Visualiseringstyper i Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

