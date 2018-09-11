--- 
title: "Ange försäljningsavtal"
description: "I den här proceduren visas hur du skapar en försäljningsavtal där en av dina kunder åtar sig att köpa en produkt för ett avtalat belopp över tid i utbyte mot speciella rabatter."
author: omulvad
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 8c11164f7edb8e05b93f3c58b9707c0bf2482228
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="enter-sales-agreements"></a>Ange försäljningsavtal

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren beskrivs hur du skapar ett försäljningsavtal som ålägger en av dina kunder att köpa en produkt för ett

överenskommet belopp över tiden i utbyte mot eventuella rabatter som avtalats. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.


## <a name="set-up-sales-agreement-header"></a>Ställ in försäljningsavtalshuvudet
1. Gå till försäljning och marknadsföring > Försäljning avtal > försäljningsavtal.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Klassificering av försäljningsavtal.
7. Klicka på länken på den valda raden i listan.
8. Expandera avsnittet Allmänt.
9. I fältet Standardutfästelse, välj Utfästelse för produktvärde.
    * En utfästelsetyp är ett obligatoriskt kriterium som du måste tilldela till avtalet för att definiera hur avtalskontraktet uppfylls. De fyra fördefinierade typer kan du ställa in kundens åtagande mål, uttryckt som en kvantitet eller ett värde. Kvantitetutfästelsetypen kan endast tillämpas på en specifik produkt, men de hierarkibaserade typerna kan användas för både försäljning och icke-specifika produkter.  
10. I fältet Utgångsdatum, ange datumet till ett framtida datum när du vill att avtalet ska upphöra.
11. Klicka på OK.

## <a name="set-up-product-value-commitment-lines"></a>Ställ in utfästelserader för produktvärde
1. Klicka på Lägg till rad.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
3. Hitta och markera önskad post i listan.
4. Klicka på länken på den valda raden i listan.
    * Typen av åtagande som du har valt för avtalet påverkar den typ av information som du kan ange för avtalsraderna. För exempelvis en värde-baserade avtal måste du ange det totala nettobeloppet (i den överenskomna valuta) för vilken kunden förbinder sig att köpa varor från dig. I det här exemplet är fälten Kvantitet och Enhet på raden inte tillgängliga eftersom du skapar ett avtal för att kunden om att köpa för ett visst värde av en produkt.   
5. I fältet Nettobelopp, ange penningbeloppet som kunden har åtagit sig att köpa för.
6. I fältet Rabatt i procent, ange en procentsats som ska användas för kundens försäljningsorderrader, som är kopplade till detta avtal.
7. Expandera avsnittet Radinformation.
8. Välj Ja i fältet Max framtvingas.
    * Om du väljer Max framtvingas innebär att det totala beloppet för alla försäljningsorderrader som använder utfästelsens särskilda priser, rabatter och/eller betalningsvillkor inte får överstiga beloppet som anges på utfästelsen.  
    * Minsta och högsta frisläppningsbeloppen anger ett värdeintervall som måste säljas på varje försäljningsorder som använder det valda avtalet.   
9. Expandera huvudavsnittet Försäljningsavtal.
    * Om inte avtalets status anges till Giltighet kan försäljningsorder inte kopplas till avtalet och kan därför inte bidra till uppfyllandet av avtalet. Du kan ändra status manuellt i detta skede. Emellertid ändras statusen normalt när du bekräftar avtalet för kunden.  
10. Klicka på Försäljningsavtal i åtgärdsfönstret.
11. Klicka på Bekräftelse.
    * Kontrollera att Ja är valt för alternativet Markera avtal som giltigt.  
12. Välj Ja i fältet Skriv ut rapport.
13. Klicka på OK.
14. Stäng sidan.
    * Avtalet är nu effektivt och du kan börja att länka kundens order till avtalet för att motboka mot det utfästa målet.  


