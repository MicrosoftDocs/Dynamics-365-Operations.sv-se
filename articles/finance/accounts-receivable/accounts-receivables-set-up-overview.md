---
title: Konfigurera Kundreskontra och Kredit och inkasso
description: Konfigurera Kundreskontra och Kredit och inkasso för att följa fakturor och inkommande betalningar från kunder.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CashDisc, CollectionLetterCourse, CreditCardProcessors, CustAgingSnapshot, CustBankAccounts, CustCollections, CustCollectionsAgent, CustCollectionsPool, CustGroup, CustParameters, CustPaymMode, CustPosting, CustVendReportInterval, Interest, PaymTerm, Reasons
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 24631
ms.assetid: 8c1fc7c5-b461-41ed-b102-2648cc58eb0b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b0593f993b12bf5448a4f8d6a564d808f85d0548
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180023"
---
# <a name="configure-accounts-receivables-and-credit-and-collections"></a>Konfigurera Kundreskontra och Kredit och inkasso

[!include [banner](../includes/banner.md)]

Konfigurera Kundreskontra och Kredit och inkasso för att följa fakturor och inkommande betalningar från kunder.

Du kan ställa in kundgrupper, kunder, bokföringsprofiler, olika betalningsalternativ, räntefakturor, kravbrev, provisioner, parametrar angående kunder, avgifter, leveranser och destinationer, växlar och andra typer av kundreskontra- och kredit och inkassoinformation.
Följande tabell visar sidorna som har stöd för konfiguration och underhåll av kundreskontra och kredit och inkasso. Tabellposterna är ordnade efter uppgift och sedan i bokstavsordning efter sidnamn.

> [!NOTE]
> Du kan inte gå till vissa sidor i tabellen nedan såvida inte data eller parameter har registrerats på andra sidor.

| Uppgift                                                 | Sidnamn                            | Användning                                                                                                                                                                                                                                                                             |
|------------------------------------------------------|--------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurera obligatorisk kundreskontrainformation | Parametrar för kundreskontra       | Konfigurera parametrar för modulen Kundreskontra.                                                                                                                                                                                                                             |
|                                                      | Arbetsflöden för kundreskontra        | Skapa ett arbetsflöde eller ändra ett befintligt arbetsflöde.                                                                                                                                                                                                                                      |
|                                                      | Kundgrupper                      | Skapa och underhåll grupper av kunder som har gemensamma nyckelparametrar. Dessa inkluderar betalningsvillkor, kvittningsperioder, redovisningskonton för lagerbokföring, momsgrupp och standardkontoinställningar.                                                                                  |
|                                                      | Bokföringsprofil för kund             | Ställ in bokföringsprofiler som styr bokföringen av kundtransaktionerna i redovisningen.                                                                                                                                                                              |
|                                                      | Formulärinställningar                           | Definiera formatet på informationen i olika dokument som är kopplade till dina kunder, t.ex. försäljningsorder, plocklistor, följesedlar och fakturor.                                                                                                                            |
|                                                      | Betalningsmetoder - kund        | Skapa och underhåll information om kundernas betalningsmetoder.                                                                                                                                                                                                           |
|                                                      | Betalningsvillkor                     | Definiera de betalningsvillkor du tilldelar order, inköpsorder, kunder och leverantörer i antingen Kundreskontra eller Leverantörsreskontra.                                                                                                                           |
|                                                      |                                      |                                                                                                                                                                                                                                                                                   |
| Konfigurera kundreskontrajournaler             | Journalnamn                        | Skapa och hantera mallar för journaler. Detta inkluderar hantering av bokföringsrestriktioner för utvalda användare eller användargrupper.                                                                                                                                                 |
|                                                      |                                      |                                                                                                                                                                                                                                                                                   |
| Konfigurera kundfakturor                        | Faktureringskoder                        | Ställ in valfria koder för faktureringsavgifter som ska användas på rader i fritextfaktura.                                                                                                                                                                                                      |
|                                                      | Kod för avgifter                         | Ställa in koder för avgifter som ska användas på försäljnings- och inköpsorder, t.ex. fakturaavgifter, frakt och försäkring.                                                                                                                                                            |
|                                                      | Sidfotstext                          | Ange sidfotstext för en utskriftshanteringspost på flera språk. När ett dokument skrivs ut bestämmer språket i dokumentet vilket språk som används i sidfotstexten.                                                                                                   |
|                                                      | Formulärnoteringar                           | Redigera den standardtext som visas på olika sidor som organisationen använder, t.ex. fakturor, försäljningsorder och räntefakturor.                                                                                                                                         |
|                                                      | Formulärinställningar                           | Definiera sidnoteringsparametrar för offerter, bekräftelser, plocklistor, följesedlar, kundfakturor, fritextfakturor och räntefakturor.                                                                                                                               |
|                                                      | Parametrar för formulärsortering              | Ställa in sorteringsordning vid utskrift av flera fakturor, t.ex. efter fakturakonto och försäljningsordernummer                                                                                                                                                                          |
|                                                      | Inställning för utskriftshantering               | Konfigurera utskriftshantering av originalposter, kopior och villkorliga inställningar. Denna information styr hur dokument som försäljningsorder och inköpsorder skrivs ut under bekräftelseprocessen.                                                               |
|                                                      |                                      |                                                                                                                                                                                                                                                                                   |
| Konfigurera kundbetalningar                        | Kassarabatter                       | Ställa in och hantera kassarabattkoder som är kopplade till kund- och leverantörskonton och tillämpas på försäljningsorder och inköpsorder.                                                                                                                                      |
|                                                      | Kreditkortsföretag               | Ställa in information om kreditkortsföretag som auktoriserar kreditkort som används vid betalning av försäljningsorder.                                                                                                                                                     |
|                                                      | Valutor                           | Skapa och visa de valutor som din organisation använder.                                                                                                                                                                                                                       |
|                                                      | Valutakurser              | Skapa och underhåll lämpliga valutakurser mellan redovisningsvalutan och andra valutor.                                                                                                                                                                              |
|                                                      | Koncernintern redovisning              | Skapa en lista över vilka konton den juridiska personen kan bokföra på. Du måste ställa in debet- och kreditkonton, och även ställa in den journal där transaktionerna införs i den andra juridiska personen.                                                                             |
|                                                      | Betalningsmetoder - kund        | Skapa och underhåll information om kundernas betalningsmetoder. Mer information finns i [upprätta kundens betalningsmetod](tasks/establish-customer-method-payment.md).                                                                                             |
|                                                      | Organisationshierarkier             | Ställa in en organisationshierarki för centraliserade betalningar.                                                                                                                                                                                                                        |
|                                                      | Syften för organisationshierarki      | Ange ett syfte för centraliserade betalningar.                                                                                                                                                                                                                                       |
|                                                      | Betalningsdagar                         | Ange antalet betalningsdagar som används för att beräkna förfallodatum för betalningar som du ska få från kunder eller göra till leverantörer.                                                                                                                                                |
|                                                      | Betalningsavgift                          | Skapa och underhåll betalningsavgifter som är kopplade till kunder, t.ex. avgifter för växlar.                                                                                                                                                                         |
|                                                      | Betalningsavgiftsinställning                    | Ställ in betalningsavgifter för olika kombinationer av banker, betalningsmetoder, typer av remissa, betalningsspecifikationer, valutor och datumintervall.  Mer information finns i [upprätta kundens betalningsavgifter](tasks/establish-customer-payment-fees.md).                                                                                   |
|                                                      | Betalningsplaner                    | Skapa betalningsplaner som du använder för att schemalägga avbetalningar från kunder och till leverantörer.                                                                                                                                                                       |
|                                                      | Betalningsspecifikation                | Skapa och visa betalningsspecifikationskoder för den betalningsmetod som du har valt på sidan Betalningsmetoder. Du definierar betalningsspecifikationskoder enligt ditt avtal med den bank som angivits för den valda betalningsmetoden.                    |
|                                                      | Transaktionstext                     | Skapa transaktionstext för automatisk bokföring i Redovisningsmodulen. Du kan ställa in transaktionstexter på olika språk.                                                                                                                                                           |
|                                                      | Översättningar                         | Skapa text på ett annat språk. Du kan översätta alla texter avsedda för externa användare (t.ex. betalningsvillkor, leveransvillkor och leveranssätt) till ett eller flera språk.                                                                                                    |
|                                                      |                                      |                                                                                                                                                                                                                                                                                   |
| Konfigurera kundbetalningsformat                 | Växellayout              | Ställ in layouten på växlarna för det bankkonto du har valt på sidan Bankkonton.                                                                                                                                                                          |
|                                                      | Checklayout                         | Ställ in layouten på checkarna för det bankkonto du har valt på sidan Bankkonton.                                                                                                                                                                                     |
|                                                      | Filformat för betalningsmetod  | Välj vilket format för import-, export-, retur- och remissafiler som ska användas vid kundbetalningar.                                                                                                                                                                                          |
|                                                      | Betalningsmetoder - kund        | Skapa och underhåll information om kundernas betalningsmetoder.                                                                                                                                                                                                           |
|                                                      | Signatur                            | Lägg till, ändra eller ta bort signaturbildfiler, till exempel .bmp-, .jpg- eller .gif-filer. Bildfiler med signaturer skrivs ut på checkar som officiella signaturer för juridisk person.                                                                                                             |
|                                                      |                                      |                                                                                                                                                                                                                                                                                   |
| Konfigurera kundreskontrastatistik           | Definitioner för åldersfördelningsperiod             | Ställa in och hantera användardefinierade åldersfördelningsperioder som används för att analysera kund- och leverantörskontonas förfallotider, baserat på ett datum som du anger. Mer information finns i [Ställ in och generera åldersfördelningsinformation för kundreskontra](tasks/set-up-accounts-receivable-aging-information.md).                                                           |
|                                                      | Affärsstatistik                  | Ställ in frågor om affärsstatistik som kan hjälpa dig att analysera organisationens resultat.                                                                                                                                                                              |
|                                                      | Affärsstatistikdata             | Visa data i ett rutnätsformat för vald affärsstatistik.                                                                                                                                                                                                                     |
|                                                      |                                      |                                                                                                                                                                                                                                                                                   |
| Underhåll kundinformation                     | Adressbok                         | Ange eller visa information om potentiella kunder, leads, affärsmöjligheter, kunder, kontaktpersoner, konkurrenter och medarbetare.                                                                                                                                                          |
|                                                      | Kundbankkonton               | Skapa och hantera kundbankkonton.                                                                                                                                                                                                                                         |
|                                                      | Kundgrupper                      | Skapa och underhåll grupper av kunder som har gemensamma nyckelparametrar. Dessa inkluderar betalningsvillkor, kvittningsperioder, redovisningskonton för lagerbokföring, momsgrupp och standardkontoinställningar.                                                                                  |
|                                                      | Kunder                            | Skapa och hantera kundkonton för de kunder som organisationen samarbetar med.                                                                                                                                                                                    |
|                                                      | Skriv ut hanteringsinställningar               | Konfigurera utskriftshantering av originalposter, kopior och villkorliga inställningar. Denna information styr hur dokument som försäljningsorder och inköpsorder skrivs ut under bokföringsprocessen.                                                                    |
|                                                      |                                      |                                                                                                                                                                                                                                                                                   |
| Konfigurera Kredit och inkasso                   | Parametrar för kundreskontra       | Ställ in parametrar för modulen Kredit och inkasso.                                                                                                                                                                                                                          |
|                                                      | Ärendekategorier                      | Ställ in en ärendekategori som används för inkassoärenden.                                                                                                                                                                                                                   |
|                                                      | Kravbrev                    | Skapa och hantera kravbrevsserier och koppla dem till kravbrevsrader.                                                                                                                                                                                      |
|                                                      | Inkassohandläggare                    | Ställa in insamlingsagenter som ska användas på sidan Inkasso.                                                                                                                                                                                                                        |
|                                                      | Inkassoteam                     | Ställ in ett inkassoteam som representerar arbetarna som kan ställas in som handläggare. Ett team med namnet Inkasso ställs in automatiskt i parametrar för Kundreskontra om inget team finns.                                                                                 |
|                                                      | Ögonblicksbild av åldersfördelningen för kunder              | Skapa en ögonblicksbild av åldersfördelningen för kunder. En ögonblicksbild av åldersfördelning består av beräknade åldersfördelningssaldon för en grupp med kunder vid en viss tidpunkt. Det här steget kräver att en definition för en åldersfördelningsperiod ställs in.                                                                           |
|                                                      | Kundkontakter och e-postinställningar | Ställ in kontakter för kunder med deras e-postadresser. Dessa adresser visas på sidan Inkasso och används för att skapa e-postmeddelanden till kunder. Ställ in också in en standardkontakt för Inkasso för varje kund som visas först på sidan Inkasso. |
|                                                      | Kundpooler                       | Ställa in kundpooler, som är frågor som definierar en grupp med kundkonton som kan visas och hanteras för samlingar eller åldersfördelningsprocesser.                                                                                                                           |
|                                                      | Bokföringsprofil för kund             | Ställ in profiler som styr bokföringen av kundtransaktionerna i redovisningen.                                                                                                                                                                                      |
|                                                      | Kundorsakskoder                | Skapa orsakskoder för kund.                                                                                                                                                                                                                                                    |
|                                                      | Orsakskoder för kundavskrivning      | Ställ in kundavskrivningskoder som ska användas för avskrivningstransaktioner.                                                                                                                                                                                             |
|                                                      | Formulärinställningar                           | Definiera formulärnoteringsparametrar för offerter, bekräftelser, plocklistor, följesedlar, kundfakturor, fritextfakturor och räntefakturor.                                                                                                                               |
|                                                      | Intresse                             | Ställ in och hantera räntekoder.                                                                                                                                                                                                                                                 |
|                                                      | Information om NSF.                     | Ställ in information om NSF för bankkontot som ska användas när en betalning markeras som en NSF-transaktion på sidan Inkasso.                                                                                                                                              |
|                                                      | Information om säljare              | Ställ in e-postadress för säljare. Dessa adresser visas på sidan Inkasso och används för att skicka e-post till en säljare från den sidan.                                                                                                                |


Mer information finns i [Kredit och inkasso i kundreskontra](collections-credit-accounts-receivable.md).


