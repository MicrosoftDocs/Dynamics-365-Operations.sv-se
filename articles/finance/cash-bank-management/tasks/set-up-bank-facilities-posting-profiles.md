---
title: Ställ in bankkreditlimiter och bokföringsprofiler för garanti
description: Denna uppgift skapar en bankkreditlimit och en bokföringsprofil som behövs för att bearbeta en garanti.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0987ae1e9cfbb1e2d2a957a5fd1ad82257292c0a
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804112"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a>Ställ in bankkreditlimiter och bokföringsprofiler för garanti

[!include [banner](../../includes/banner.md)]

Denna uppgift skapar en bankkreditlimit och en bokföringsprofil som behövs för att bearbeta en garanti.



I den här uppgiften används demonstrationsföretaget USMF. 




## <a name="general-ledger-parameter"></a>Redovisningsparameter
1. Gå till **Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering**.
2. Expandera **bankdokument** avsnittet.
3. Välj alternativet **Aktivera garanti**.
4. I fältet **Transaktionsjournal**, öppna sökningen genom att klicka på den nedrullningsbara knappen.
5. Hitta och markera önskad post i listan.
6. Klicka på länken på den valda raden i listan.
7. Klicka på fliken **Nummersekvenser**.
    * Definiera nummerseriekoden för referenserna Garantinummer och Transaktionsnummer för garanti  
8. Klicka på **Spara**.
9. Stäng sidan.

## <a name="create-bank-facility"></a>Skapa bankkreditlimit
1. Gå till **Kassa- och bankhantering > Inställningar > Bankkreditlimiter**.
2. Klicka på **Ny**.
3. I fältet **Kreditlimitgrupp**, ange bankkreditlimitgruppens namn för garantitransaktionen.
4. I fältet **Beskrivning** anger du ett värde.
5. Klicka på **Spara**.
6. Klicka på fliken **Kreditlimittyper**.
7. Klicka på **Ny**.
8. I fältet **Kreditlimittyp**, ange namnet på bankkreditlimittypen som är relaterad till bankkreditlimitavtalet.
9. I fältet **Beskrivning** anger du ett värde.
10. I fältet **Kreditlimittyp**, öppna sökningen genom att klicka på den nedrullningsbara knappen.
11. Hitta och markera önskad post i listan.
12. Klicka på länken på den valda raden i listan.
13. I fältet **Kreditlimitens natur**, välj ett alternativ.
14. Klicka på **Spara**.
15. Stäng sidan.

## <a name="bank-posting-profile"></a>Bokföringsprofil för bank
1. Gå till **Kassa- och bankhantering > Inställningar > Bokföringsprofil för bankdokument**.
2. Klicka på **Ny**.
3. I fältet **Konto-/gruppnummer**, öppna sökningen genom att klicka på den nedrullningsbara knappen.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. I fältet **Kvittningskonto**, välj huvudkontot för kvittning.
7. I fältet **Avgiftskonto**, välj kontot för utgiftstransaktioner.
8. I fältet **Marginalkonto**, välj kontot för marginaltransaktionen.
9. I fältet **Likvideringskonto**, välj likvideringkontot för garantitransaktionen. 
10. Klicka på **Spara**.
11. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
