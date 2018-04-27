---
title: Redovisning journaltyper
description: "Det här avsnittet ger en beskrivning av de journaltyper du kan ställa in för ekonomiska journaler. Använd sidan för **journalnamn** för att ställa in journaler som du kan använda i hela Microsoft Dynamics 365 for Finance and Operations."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15631
ms.assetid: 81613b31-bc3c-43a0-8474-e01c9a482c40
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 9f8fc40f199b83a9e0cb36ce905163c3ed547057
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="ledger-journal-types"></a>Redovisningsjournaltyper

[!INCLUDE [banner](../includes/banner.md)]

Det här avsnittet ger en beskrivning av de journaltyper du kan ställa in för ekonomiska journaler. Använd sidan för **journalnamn** för att ställa in journaler som du kan använda i hela Microsoft Dynamics 365 for Finance and Operations.

| Journaltyp                      | Syfte                       | Registrera transaktioner på denna sida                                |
|-----------------------------------|-------------------------------|----------------------------------------------------------------|
| Allokering                        | Skapa allokeringstransaktioner i en allokeringsjournal. Innan du kan skapa en fördelning journal, måste du skapa en periodiseringsregeln på **redovisning periodiseringsregeln** sida.      | Bearbeta allokeringsbegäran             |
| Godkännande                          | Bokföra leverantörsfakturor som har godkänts för lämpliga redovisningskonton.  | Fakturagodkännandejournal                                       |
| Återföring av bankcheck               | Återför en bokförd check. För att använda denna typ av journal, välj **Använd granskningsprocessen för betalningsåterföringar** på **Kassa och bank hanteringsparametrarna** sidan.   | Kontrollera återföringar, betalningsåterföring                   |
| Annullering av insättningskvitto    | Annullera ett insättningskvitto. För att använda denna typ av journal, välj **Använd granskningsprocessen för insättningsblanketten betalning avbokning** på **Kassa och bank hanteringsparametrarna** sidan.   | Betalningsannulleringar för insättningskvitto            |
| Budget                            | Bearbeta budgetanslag. För att använda denna typ av journal, välj **Aktivera anslag** på **redovisning parametrar sidan** . Budgeten journalanteckningar kommer att innehålla information som är baserad på reskontraförda konton som definierats i **konteringstypen definitioner** sidan.                                                        |                                                                |
| Kund accepterar växel  | Skapa kundgodkännandetransaktioner för växlar.             | Journal för utställda växlar, Journal för återutställda växlar |
| Kundbankremissa          | Skapa en växelremissafil som kan skickas till din organisations bank. För att använda denna typ av journal, radera **automatisk kvittning** på **kundfordringar** **parametrar sidan** .            | Remittering                                                     |
| Kund ställer ut växel    | Skapa transaktioner för när kund ställer ut växel. För att använda denna typ av journal, **Skapa och kontera rita journalen automatiskt när man konterar fakturor** på **betalningssätt – kunder** sidan.   | Journal för utställda växlar                                  |
| Kundbetalning                  | Skapa kundbetalningstransaktioner.                             | Betalningsjournal             |
| Kund protesterar växel | Skapa transaktioner för när kund bestrider växel.                    | Journal för växelprotester                               |
| Kund ställer ut ny växel  | Skapa transaktioner för när kund ställer ut ny växel.                     | Journal för återutställda växlar                                |
| Kund löser in växeln  | Skapa transaktioner för när kund löser in växel.                       | Journal för inlösta växlar                                |
| Dagligen                             | Skapa dagliga transaktioner i en allmän journal.                          | Allmän journal                                                |
| Eliminering                       | Skapa elimineringstransaktioner i en elimineringsjournal. För att använda denna typ av journal, välj att **använda för finansiella uteslutningsmetoden** och **använda för ekonomisk konsolideringsprocessen** alternativ på **juridiska personer** sidan. Innan du kan använda denna journaltyp, måste du skapa en redovisningselimineringsregel på **redovisningselimineringsregel** sidan. | Eliminering                                                    |
| Budget för anläggningstillgång                | Skapa budgetregisterposter för anläggningstillgångar.                                                                                                                                                                                                                                                                                                                 | Budget för anläggningstillgång                                             |
| Fakturaregister                  | Registrera basinformation om leverantörsfakturor.                                                                                                                                                                                                                                                                                                           | Fakturaregister                                               |
| Löneutbetalning              | Utfärda betalningar som baseras på lön betalar uttalanden. Du kan inte ange transaktioner i journalen manuellt. Du måste skapa löneutdrag och sedan skicka dessa utdrag för betalning.                                                                                                                                                              |                                                                |
| Periodisk                          | Skapa periodiska transaktioner för den periodiska journalen.                                                                                                                                                                                                                                                                                                      | Periodiska journaler                                              |
| Bokför anläggningstillgångar                 | Bokföra anläggningstillgångar.                                                                                                                                                                                                                                                                                                                              | Anläggningstillgångar                                                   |
| Projekt - utgifter                | Skapa utgiftstransaktioner för projekt.                                                                                                                                                                                                                                                                                                                        | Utgift                                                        |
| Statistiktransaktioner            | Skapa statistiktransaktioner.                                                                                                                                                                                                                                                                                                                            |                                                                |
| Leverantörsbankremissa            | Skapa en remissafil för en skuldsedel som kan skickas till din organisations bank.                                                                                                                                                                                                                                                                      | Remissajournal                                             |
| Leverantörsutbetalning               | Skapa leverantörsutbetalningstransaktioner.                                                                                                                                                                                                                                                                                                                    | Betalningsjournal                                                |
| Leverantör ställer ut skuldsedel       | Dra leverantörsskuldsedlar som en betalningsmetod. För att använda denna typ av journal, **Skapa och kontera rita journalen automatiskt när man konterar fakturor** på **betalningssätt – säljare** sida.                                                                                                                                          | Journal för utställda skuldsedlar                                   |
| Leverantörsfakturapool utan bokföring | Skapa leverantör faktura transaktioner som ännu inte har bokförts till en tillfällig ankomst.                                                                                                                                                                                                                                                             | Leverantörsfakturapool utan bokföringsdetaljer                  |
| Leverantörsfakturapool               | Skapa transaktioner för leverantörsfakturapool.                                                                                                                                                                                                                                                                                                                    |                                                                |
| Registrering av leverantörsfaktura          | Bokföra leverantörsfakturor som är i en journal.                                                                                                                                                                                                                                                                                                                 | Fakturajournal                                                |
| Leverantör ställer ut ny skuldsedel     | Återutställa en skuldsedel som tidigare har inlösts av din organisations bank.                                                                                                                                                                                                                                                                      | Journal för återutställda skuldsedlar                                 |
| Leverantör likviderar skuldsedel     | Skapa transaktioner för leverantörslikvid av skuldsedel.                                                                                                                                                                                                                                                                                                          | Journal för likviderade skuldsedlar                                 |






