---
title: Konton för automatiska transaktioner
description: I det här avsnittet beskrivs hur konton för automatiska transaktioner används för bokföring till och med Microsoft Dynamics 365, och innehåller exempel på nyckelkonton för automatiska transaktioner.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cecbeb769235e525390cc7a66800a9b0d55d78a9
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/19/2022
ms.locfileid: "8014058"
---
# <a name="accounts-for-automatic-transactions"></a>Konton för automatiska transaktioner

Sidan **Konton för automatiska transaktioner** (**Redovisning &gt; Bokföringsinställningar &gt; Konton för automatiska transaktioner**), används för att definiera standard huvudkonton som används för varje bokföringstyp i systemet. Även om de flesta bokföringstyper kan konfigureras på en modulspecifik eller funktionsspecifik sida, kan vissa bokföringstyper endast konfigureras på sidan **Konton för automatiska transaktioner**.

Du kan t.ex. ange huvudkontot som används för bokföringstypen **Kundsaldo**, fältet **Sammanfattning** på sidan **Bokföringsprofil för kund** och använda ett annat huvudkonto för varje kundprofil. På detta sätt har du mer finkontroll över bokföringarna. Å andra sidan kan du endast ange felkontot på sidan **Konton för automatiska transaktioner**.

När du öppnar sidan **Konton för automatiska transaktioner** i en ny juridisk person är kontolistan tom. Du kan lägga till de vanligaste bokföringstyperna som ska konfigureras på sidan genom att välja knappen **Skapa standardtyper**. För varje rad kan du sedan välja huvudkontot på fältet **huvudkonto**. Om fältet **huvudkonto** lämnas tomt för en bokföringstyp och du inte har konfigurerat ett huvudkonto på en modulspecifik eller funktionsspecifik sida visas ett felmeddelande när du bokför en transaktion som använder bokföringstypen.  Vanligtvis visas meddelandet "Kontot för \[bokföringstyp\] går inte att hitta."

## <a name="default-posting-types"></a>Standardbokföringstyper

Följande tabell innehåller exempel på de standardbokföringstyper som skapas när du väljer **Skapa standardtyper** på sidan **Konton för automatiska transaktioner**. Här visas exempel på huvudkonton och beskrivningar. "Debet/Kredit?" kolumnen anger om transaktionen normalt bokför en debet eller kredit. I vissa fall kan en transaktion bokföra antingen en debet eller en kredit. Kolumnen Clearingkonto visar att bokföringstypen är ett clearingkonto. Om bokföringstypen är ett clearingkonto, beloppet som bokförs i kontot återförs automatiskt när en senare transaktion bokförs.

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | Beskrivning |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Öresdifferens i rapporteringsvaluta | 618160 | Diverse utgifter | Utgift | Båda | Nej | Denna bokföringstyp används när en öresdifferens inträffar när ett transaktionsbelopp i en utländsk valuta översätts till rapporteringsvalutan. |
| Öresdifferens i redovisningsvaluta | 618160 | Diverse utgifter | Utgift | Båda | Nej | Denna bokföringstyp används när en öresdifferens inträffar när ett transaktionsbelopp i en utländsk valuta översätts till redovisningsvaluta. |
| Felkonto | 999999 | Felkonto | Utgift | Båda | Nej | Denna bokföringstyp används när ett fel inträffar i systemet. Kontot ska valideras varje period och eventuella fel ska lösas. |
| Årsslutsresultat | 300160 | Balanserade vinstmedel | Eget kapital | Båda | Nej | Denna bokföringstyp används när processen för årsbokslut körs för att flytta saldot för kontona för typen **Resultaträkning** till huvudkontot som väljs för resultatet vid årets slut. |
| Kundkassarabatt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej | Bokföringstypen som definieras på **kontona för automatiska transaktioner** som sida inte används. Ett huvudkonto krävs när kassarabatter konfigureras i kundreskontra.|
| Leverantörskassarabatt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Inte tillämpligt | Nej | Bokföringstypen som definieras på **kontona för automatiska transaktioner** som sida inte används. Ett huvudkonto krävs när kassarabatter konfigureras i leverantörsreskontra. |

## <a name="additional-posting-types"></a>Ytterligare bokföringstyper

Följande tabell innehåller exempel på ytterligare bokföringstyper som måste konfigureras om du tänker använda de relaterade funktionerna. För dessa bokföringstyper finns ingen konfiguration av bokföringsprofilen tillgänglig i en annan modul. "Debet/Kredit?" kolumnen anger om transaktionen normalt bokför en debet eller kredit. I vissa fall kan en transaktion bokföra antingen en debet eller en kredit. Kolumnen Clearingkonto visar att bokföringstypen är ett clearingkonto. Om bokföringstypen är ett clearingkonto, beloppet som bokförs i kontot återförs automatiskt när en senare transaktion bokförs.

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | Beskrivning |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Saldokonto för konsolideringsdifferens | 801200 | Vinst och förlust - Omvärdering | Utgift | Båda | Nej | Denna bokföringstyp används när du utför en konsolidering som inbegriper en valutaomvärdering och öresdifferenser uppstår under omvärderingen. |
| Resultatkonto för konsolideringsdifferenser | 801200 | Vinst och förlust - Omvärdering | Utgift | Båda | Nej | Denna bokföringstyp används när du utför en konsolidering som inbegriper en valutaomvärdering och öresdifferenser uppstår under omvärderingen. |
| Enhetsintern – debet | 133500 | Enhetsintern fordring | Tillgång | Debet | Nej | Denna bokföringstyp används när du väljer en balanseringsdimension på **redovisningssidan** och dimensionen inte balanserar i en transaktion som bokförs. |
| Enhetsintern – kredit | 233500 | Enhetsintern skuld | Skulder | Kredit | Nej | Denna bokföringstyp används när du väljer en balanseringsdimension på **redovisningssidan** och dimensionen inte balanserar i en transaktion som bokförs. |
