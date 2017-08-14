---
title: Lagerplatser
description: "Lagerplatser används med grundläggande lagerstyrning (Lagerstyrningssystem I) för att bestämma var artiklar lagras och var artiklar plockas i ett Lagerstyrningssystem I-lagerställe."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSLocation
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 95d93c9d471cc86877f35340693c171958db71df
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---

# <a name="inventory-locations"></a>Lagerplatser

[!include[banner](../includes/banner.md)]


Lagerplatser används med grundläggande lagerstyrning (Lagerstyrningssystem I) för att bestämma var artiklar lagras och var artiklar plockas i ett Lagerstyrningssystem I-lagerställe.

Det här ämnet gäller funktioner i modulen Lagerhantering. Den gäller inte funktioner i modulen Lagerstyrning.

Termen plats hänvisar till det ställe som artiklar lagras och hämtas från.

För varje plats kan stället där artikeln infogas också anges. Som standard är de samma. Artiklar infogas och hämtas vanligtvis från samma sida om en plats, men inte alltid. Artiklar som lagras i lagringsställningar infogas till exempel från en gång och hämtas från en annan. Huvudinmatningen anges av ett platsnamn, som vanligtvis bestäms av dess koordinater: lagerställe, gång, ställning, hylla och binge. Det här namnet eller ID:t kan anges manuellt eller genereras från platsens koordinater, till exempel 01-02-03-4 för gång 1, ställning 2, hylla 3, binge 4 på sidan Lagerplatser.
Platsegenskaper
-------------------

En plats har följande egenskaper:
-   Storlek (höjd, bredd, djup, och därigenom volym)
-   Plats för lagerställe, gång, ställning, hylla och binge.
-   Platstyp (bulkplats, plockplats, inlastningsplats, utlastningsplats, plats för produktionsinleverans, inspektionplats eller kanban-storlager)

Kontrolltext kan användas i onlinesystem för att bekräfta att operatören har valt rätt plats för en viss artikel. Kontrolltexten kan skapas manuellt eller som standard.

## <a name="sort-codes"></a>Sorteringskoder
Använd sorteringskoder om du vill optimera hanteringen av plockrader, som beskriver den information som krävs för att plocka artiklar från lagret, inklusive plockordning. Sorteringskoder kan innehålla gång och andra koordinater eller tilldelas manuellt för platsen.

## <a name="blocked-locations"></a>Spärrade platser
Ibland kanske du vill ange att en plats är blockerad under en tid, exempelvis under en reparation. Vid andra tillfällen kanske man vill ange blockering av endast in- eller utleverans.
Trädstruktur
--------------

På sidan Lagerplatser kan du visa lagerställelayouten i en trädstruktur baserad på koordinaterna för lagerplatser, i ett definierat bildskärmsformat.
Hantera lagerplatser via formuläret Lagerställe
---------------------------------------------------

Det går att kopiera platser från ett lagerställe till ett annat och skapa platser via en guide. Innan du kör guiden bör du se till att du har definierat standardplatsnamnen på sidan Lagerställe.



<a name="see-also"></a>Se även
--------

[Skapa en ny layout för lagerställe (uppgiftsguide)](/dynamics365/unified-operations/supply-chain/inventory/tasks/create-new-warehouse-layout)




