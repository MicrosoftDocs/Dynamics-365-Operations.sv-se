---
title: "Allokeringsregler för redovisning"
description: "Den här artikeln innehåller information om allokeringsregler för redovisning. Den beskriver de olika komponenterna för dessa allokeringsregler och allokeringsmetoderna som kan användas för dem."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerAllocation, LedgerAllocationBasisRule, LedgerAllocationRequest, LedgerAllocationRule
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15402
ms.assetid: 8147e148-7c11-45ef-95c6-f9889a875b54
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: cf723381ed2f9696512d17af7e882582cbfcb49e
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="ledger-allocation-rules"></a>Allokeringsregler för redovisning

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller information om allokeringsregler för redovisning. Den beskriver de olika komponenterna för dessa allokeringsregler och allokeringsmetoderna som kan användas för dem.

Redovisningallokeringsregler används för att beräkna och automatiskt generera allokeringsjournaler och kontoposter för allokering av redovisningssaldon eller fasta belopp. Allokeringmetoder kan vara variabla eller fasta. Följande allokeringsmetoder kan användas för redovisningallokeringsregler:

-   **Bas** – Den här variabelmetoden används när allokeringen beror på det verkliga redovisningssaldot, baserat på filterkriterier. Du kan till exempel allokera utgifter baserat på varje avdelnings försäljning i proportion till den totala försäljningen.
-   **Fast procentsats** och **Fast vikt** – För dessa metoder anges allokeringsprocent eller vikt direkt för regeln. Till exempel kan annonseringsutgifter allokeras så att avdelning A får 70 procent av annonseringsutgifterna och avdelning B får 30 procent.
-   **Lika** – Den här metoden fördelar beloppet jämnt på varje definierad destination. Om till exempel destination har definierats för avdelning A och avdelning B, kan annonseringsutgifter allokeras så att både avdelning A och avdelning B får 50 procent av annonseringsutgifterna.

Om Bas används som allokeringsmetod för en allokeringsregel är lika med , måste du också definiera en separat basallokeringsregler för redovisning. Processen ”Bearbeta allokeringsbegäran" gör det möjligt för användare att bearbeta redovisningallokeringsregeln och förhandsgranska de resulterande allokeringsjournalposterna innan de bokförs eller ta bort de beräknade allokeringarna.

## <a name="components-of-ledger-allocation-rules"></a>Komponenter för allokeringsregler för redovisning
En allokeringsregel har fyra huvudsakliga komponenter – allmän, källa, destination och motbokning. En ytterligare komponent, allokeringsbasregler för redovisning, krävs om Bas används som allokeringsmetod. Varje komponent omfattar viktig information som krävs för att bearbeta processallokeringarna.

-   **Allmän** – Den allmänna komponenten är där användaren anger alternativ, bland annat allokeringsmetod, inställningar för koncernintern regel och om regeln är aktiv eller inte.
-   **Källa** – Denna komponent är där användaren anger källadatan för allokeringen. Allokeringen kan baseras på redovisningssaldo (**Datakälla** = **Redovisning**) eller fasta belopp (**Datakälla** = **Fast värde**). När **Datakälla** ställs in på **Redovisning** måste källafiltervillkoret definieras för redovisningallokeringsregeln (exempelvis för annonseringsutgifterna).
-   **Destination** – Denna komponent anger hur resultatet från allokeringsberäkningen ska fördelas och bokföras. Till exempel kan det finnas en destinationsrad för varje avdelning.
-   **Motboka** Denna komponent definierar hur huvudkonton och dimensioner ska bestämmas för motbokningsposter som överensstämmer med posterna. användardefinierade alternativ används vanligtvis i stället för de konton och dimensioner som baseras på källan. När **Datakälla** är inställd på **Fast värde**, kan inte **Källa** användas som ett alternativ.
-   **Basallokeringsregler för redovisning** – Dessa regler använder sin egen källafiltervillkor som avgör vilka redovisningssaldon som ska användas för allokering (exempelvis intäkt per avdelning.) Varje allokeringsbasregel kan användas för många allokeringsregler.





