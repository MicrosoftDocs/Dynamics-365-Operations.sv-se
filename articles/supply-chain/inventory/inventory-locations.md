---
title: Lagerplatser
description: Lagerplatser används med grundläggande lagerstyrning (Lagerstyrningssystem I) för att bestämma var artiklar lagras och var artiklar plockas i ett Lagerstyrningssystem I-lagerställe.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSLocation, WMSBlockingCause, WHSLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8d5459e37b5827b6a2ff07c892c2ff25b76ecd6
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187492"
---
# <a name="inventory-locations"></a>Lagerplatser

[!include [banner](../includes/banner.md)]

Lagerplatser används med grundläggande lagerstyrning (Lagerstyrningssystem I) för att bestämma var artiklar lagras och var artiklar plockas i ett Lagerstyrningssystem I-lagerställe.

Det här ämnet gäller funktioner i modulen Lagerhantering. Den gäller inte funktioner i modulen Lagerstyrning.

Termen plats hänvisar till det ställe som artiklar lagras och hämtas från.

För varje plats kan stället där artikeln infogas också anges. Som standard är de samma. Artiklar infogas och hämtas vanligtvis från samma sida om en plats, men inte alltid. Artiklar som lagras i lagringsställningar infogas till exempel från en gång och hämtas från en annan. Huvudinmatningen anges av ett platsnamn, som vanligtvis bestäms av dess koordinater: lagerställe, gång, ställning, hylla och binge. Det här namnet eller ID:t kan anges manuellt eller genereras från platsens koordinater, till exempel 01-02-03-4 för gång 1, ställning 2, hylla 3, binge 4 på sidan Lagerplatser.
Platsegenskaper

En plats har följande egenskaper:
-   Storlek (höjd, bredd, djup, och därigenom volym)
-   Plats för lagerställe, gång, ställning, hylla och binge.
-   Platstyp (bulkplats, plockplats, inlastningsplats, utlastningsplats, plats för produktionsinleverans, inspektionplats eller kanban-storlager)

Kontrolltext kan användas i onlinesystem för att bekräfta att operatören har valt rätt plats för en viss artikel. Kontrolltexten kan skapas manuellt eller som standard.

## <a name="sort-codes"></a>Sorteringskoder
Använd sorteringskoder om du vill optimera hanteringen av plockrader, som beskriver den information som krävs för att plocka artiklar från lagret, inklusive plockordning. Sorteringskoder kan innehålla gång och andra koordinater eller tilldelas manuellt för platsen.

## <a name="blocked-locations"></a>Spärrade platser
Ibland kanske du vill ange att en plats är blockerad under en tid, exempelvis under en reparation. Vid andra tillfällen kanske man vill ange blockering av endast in- eller utleverans.

## <a name="tree-structure"></a>Trädstruktur

På sidan Lagerplatser kan du visa lagerställelayouten i en trädstruktur baserad på koordinaterna för lagerplatser, i ett definierat bildskärmsformat.

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a>Hantera lagerplatser via formuläret Lagerställe

Det går att kopiera platser från ett lagerställe till ett annat och skapa platser via en guide. Innan du kör guiden bör du se till att du har definierat standardplatsnamnen på sidan Lagerställe.



## <a name="additional-resources"></a>Ytterligare resurser

[Skapa en ny layout för lagerställe](tasks/create-new-warehouse-layout.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]