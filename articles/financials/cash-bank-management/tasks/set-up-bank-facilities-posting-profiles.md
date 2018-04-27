--- 
title: "Ställ in bankkreditlimiter och bokföringsprofiler för garanti"
description: "Denna uppgift skapar en bankkreditlimit och en bokföringsprofil som behövs för att bearbeta en garanti."
author: kweekley
manager: AnnBe
ms.date: 02/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 022b5d411b8240390c543ba726fe0d6838752944
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a>Ställ in bankkreditlimiter och bokföringsprofiler för garanti

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Denna uppgift skapar en bankkreditlimit och en bokföringsprofil som behövs för att bearbeta en garanti.



I den här uppgiften används demonstrationsföretaget USMF. 




## <a name="general-ledger-parameter"></a>Redovisningsparameter
1. Gå till Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering.
2. Expandera bankdokumentavsnittet.
3. Välj alternativet Aktivera garanti.
4. I fältet Transaktionsjournal, öppna sökningen genom att klicka på den nedrullningsbara knappen.
5. Hitta och markera önskad post i listan.
6. Klicka på länken på den valda raden i listan.
7. Klicka på fliken Nummersekvenser.
    * Definiera nummerseriekoden för referenserna Garantinummer och Transaktionsnummer för garanti  
8. Klicka på Spara.
9. Stäng sidan.

## <a name="create-bank-facility"></a>Skapa bankkreditlimit
1. Gå till Kassa- och bankhantering > Inställningar > Bankkreditlimiter.
2. Klicka på Ny.
3. I fältet Kreditlimitgrupp, ange bankkreditlimitgruppens namn för garantitransaktionen.
4. Ange ett värde i fältet Beskrivning.
5. Klicka på Spara.
6. Klicka på fliken Kreditlimittyper.
7. Klicka på Ny.
8. I fältet Kreditlimittyp, ange namnet på bankkreditlimittypen som är relaterad till bankkreditlimitavtalet.
9. Skriv ett värde i fältet Beskrivning.
10. I fältet Kreditlimittyp, öppna sökningen genom att klicka på den nedrullningsbara knappen.
11. Hitta och markera önskad post i listan.
12. Klicka på länken på den valda raden i listan.
13. I fältet Kreditlimitens natur, välj ett alternativ.
14. Klicka på Spara.
15. Stäng sidan.

## <a name="bank-posting-profile"></a>Bokföringsprofil för bank
1. Gå till Kassa- och bankhantering > Inställningar > Bokföringsprofil för bankdokument.
2. Klicka på Ny.
3. I fältet Konto-/gruppnummer, öppna sökningen genom att klicka på den nedrullningsbara knappen.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. I fältet Kvittningskonto, välj huvudkontot för kvittning.
7. I fältet Avgiftskonto, välj kontot för utgiftstransaktioner.
8. I fältet Marginalkonto, välj kontot för marginaltransaktionen.
9. I fältet Likvideringskonto, välj likvideringkontot för garantitransaktionen. 
10. Klicka på Spara.
11. Stäng sidan.


