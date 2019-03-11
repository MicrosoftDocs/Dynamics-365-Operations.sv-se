---
title: Kvitta rest
description: Du kan kvitta det belopp som återstår från kvittningsaktiviteten genom att använda detta belopp på ett redovisningskonto.
author: mikefalkner
manager: aolson
ms.date: 10/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 408a36a7cf221463b38260bd8830b422e58ccb64
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "367212"
---
# <a name="settle-remainder"></a>Kvitta rest

[!include [banner](../includes/banner.md)]

Du kan kvitta det belopp som återstår från kvittningsaktiviteten genom att använda detta belopp på ett redovisningskonto eller en annan kund. Du kan kvitta återstoden när du kvittar betalning av belopp som förts in i en journal eller när du bara kvittar öppna transaktioner.

## <a name="setting-up-defaults"></a>Ställa in standarder 
Du måste aktivera funktionen Kvitta rest och ställa in standardinställningarna innan du använder Kvitta rest

1)  Klicka på **Kundreskontra > Parametrar > Kvittningar** eller **Leverantörsreskontra > Parametrar > Kvittningar**
2)  Välj fliken **Kvittning** och klicka sedan på **Aktivera kvittning av rest**
3)  I **standardorsakskod** väljer du en standardorsakskod. Orsakskoderna måste redan ha ställts in i **Kundreskontra > Inställningar > Orsakskoder för kundavskrivning** eller **Leverantörsreskontra > Inställningar > Orsakskoder för kundavskrivning**. **Standardkonto för kvittning av rest** ska anpassas till kontot som tilldelats orsakskoden för avskrivning.
3)  Uppdatera **Standardkonto för kvittning av rest** efter behov.
4)  I **Standardjournalnamn**, välj en betalningsjournal som ska användas om du vill skapa en betalningsjournal när du bara kvittar öppna transaktioner. Om du aktiverar funktionen kvittning av rest måste du lägga till ett standardjournalnamn.

## <a name="settle-remainder-from-a-journal"></a>Kvitta rest från en journal
Om du inte aktiverar funktionen **Kvitta rest** kan du fortfarande ange en transaktion i en journal och sedan kvitta transaktioner mot dem som du har gjort tidigare. När du klickar på knappen **OK** kommer det ingående saldot på fakturan minskas med kontantbeloppet. Om kontanterna inte helt kvittar fakturan, lämnas fakturan öppen med ett återstående belopp som ska kvittas vid ett senare tillfälle.

När funktionen **Kvitta rest** är aktiverad, kan du kvitta återstående belopp på ett redovisningskonto. Du kan också överföra resten till ett annat kundkonto (för kundtransaktioner) eller öppna en annan leverantör (för leverantörstransaktioner) i stället för att låta fakturorna vara öppna. 

För att kvitta återstoden från sidan **kvittning** gör du följande:

1)  På sidan **kvittning**, markera de fakturor eller transaktioner du vill kvitta.
2)  Klicka på knappen **Kvitta rest**.
3)  En dialogruta visas med det belopp som ska kvittas mot ett redovisningskonto, det datum som ska användas för att kvitta återstoden, standardorsakskoden från parametrarna och standardkontot från parametrarna. 
4)  Välj en ny kvittningsorsak om du vill ändra standardorsaken. Kvittningskontot ändras till kontot som är kopplat till orsakskoden.
5)  Redigera kvittningskontot om du vill ändra den.
6)  Om du kvittar kundtransaktioner och du vill att återstoden ska flyttas till en annan kund väljer du en kund i **Kvitta rest mot kundkonto**. Om du kvittar leverantörstransaktioner och du vill att återstoden ska flyttas till en annan kund väljer du en leverantör i **Kvitta rest mot leverantörskonto**.
6)  Klicka på **Kvitta rest**.
7)  Sidan **Journal** visas. En extra journalrad läggs till journalen med kvitta återstående belopp som beloppet och kontot för kvittning av rest som motkonto. Om du har lagt till en kund eller leverantör så att du kan flytta kvittningsbeloppet till en annan kund eller leverantör, läggs ytterligare en rad till i journalen för att flytta kvittningsbeloppet till kunden eller leverantören.

När du bokför journalen, kvittas den öppna transaktionen helt. 

## <a name="settle-remainder-when-you-are-only-settling-open-transactions"></a>Kvitta rest när du endast kvittar öppna transaktioner
Du kan också kvitta rest när du kvittar öppna transaktioner utan en journal.

Om du vill kvitta rest gör du följande:

1)  På sidan **kvittning**, markera de fakturor eller transaktioner du vill kvitta.
2)  Klicka på **Kvitta rest**.
3)  En dialogruta visas med det belopp som ska kvittas mot ett redovisningskonto, det datum som ska användas för att kvitta återstoden, standardorsakskoden från parametrarna och standardkontot från parametrarna. 
4)  Välj en ny kvittningsorsak om du vill ändra standardorsaken. Kvittningskontot ändras till kontot som är kopplat till orsakskoden.
5)  Redigera **kvittningskontot** om du vill ändra den.
6)  Om du kvittar kundtransaktioner och du vill att återstoden ska flyttas till en annan kund väljer du en kund i **Kvitta rest mot kundkonto**. Om du kvittar leverantörstransaktioner och du vill att återstoden ska flyttas till en annan kund väljer du en leverantör i **Kvitta rest mot leverantörskonto**.
7)  Du kan också välja att skapa en betalningsjournal med kvittning rest eller bara bokföra dem utan en journal. Välj **Ja** för **Redigera i journal** för att skapa en betalningsjournal. Du kommer att kunna redigera den betalningsjournal som du skapar.
8)  Klicka på **Kvitta rest**. Om du vill skapa en journal ändras knappen till **Skapa journal**. Klicka på **Skapa journal** istället
9)  Om du har skapat en betalningsjournal kan sidan öppnas när du klickar på **Kvitta rest**. En journalrad läggs till journalen med kvitta återstående belopp som beloppet och kontot för kvittning av rest som motkonto. Om du har lagt till en kund eller leverantör så att du kan flytta kvittningsbeloppet till en annan kund eller leverantör, läggs ytterligare en rad till i journalen för att flytta kvittningsbeloppet till kunden eller leverantören.
