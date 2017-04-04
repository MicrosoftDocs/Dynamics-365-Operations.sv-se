---
title: Betalningsmetoder
description: "Varje betalningstyp som godkänner en återförsäljare måste konfigureras i butik och handel i Microsoft Dynamics 365 för operationer när systemet installeras. Det här avsnittet ger en beskrivning av betalningstyperna som du kan ställa in och processen för hur du ställer in dem."
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: MargoC
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b887fc5d03ea8982515e92725ce98cc416e56f9e
ms.openlocfilehash: 011beec07bf1ab858892ab1c374f1acf3839e877
ms.lasthandoff: 03/31/2017


---

# <a name="payment-methods"></a>Betalningsmetoder

Varje betalningstyp som godkänner en återförsäljare måste konfigureras i butik och handel i Microsoft Dynamics 365 för operationer när systemet installeras. Det här avsnittet ger en beskrivning av betalningstyperna som du kan ställa in och processen för hur du ställer in dem.

Återförsäljare kan acceptera olika typer av betalning i utbytet för produkter och tjänster som de säljer. Även om kontanter är den vanligaste betalningsformen kan också återförsäljare ta emot betalning i form av checkar, kort, verifikationer, osv. Varje betalningstyp som accepterar återförsäljaren måste konfigureras i Dynamics 365 för verksamhet – Retail när systemet installeras. I listan nedan beskrivs varje betalningstyp som ställts in i Dynamics 365 för verksamhet – Retail:

-   **Kontant** – Pengar i valutans fysiska form, som sedlar och mynt. Denna valuta kan antingen vara företagsvalutan eller butikens lokala valuta.
-   **Check** – Ett överlåtbart instrument som ger instruktioner om betalning av ett specifikt belopp i en specifik valuta och som är utställt på en specifik bank. En check är vanligtvis giltig utan tidsgräns eller i sex månader efter utfärdandet, om inte en annan giltighetsperiod anges. Denna period, varierar beroende på banken som checken ställs ut på. Det finns olika typer av checkar, som ordercheckar, kassacheckar, innehavarcheckar och korsade checkar. Du kan ställa in checkar som en betalningsmetod för varje butik. Checkar kan accepteras i den valuta som definieras på antingen företagsnivå eller butiksnivån. Du måste ställa in checkar som en betalningsmetod, innan du kan acceptera en check som betalning i en butik.
-   **Valuta** – Den primära formen av betalningsmedel förutom företagets standardvaluta. Mynt och sedlar är två former av valuta. Valutabetalningsmetoden representerar alla valutor som används i Butik och handel. Innan du kan använda den här typen av betalningsmedel måste du ställa in valutor och ange detaljhandelsväxelkurser för valutorna.
-   **Kort** – Alla typer av kort som används i Butik och handel, till exempel debetkort och kreditkort. Det är en bra idé att ställa in en kortbetalningsmetod på organisationsnivå för varje typ av kort. Sedan kan en typ av betalningsmetod ställas in för varje kort eller kortuppsättning på butiksnivå som bearbetas med samma inställningar. För att kunna använda typen av betalningsmedel Kort måste du ställa in de kort som finns på marknaden, dvs. betal- och kreditkort som Visa, Master och Euro, innan de kan godkännas som betalning i en butik.
-   **Kreditfaktura** – Kreditfakturor som utfärdas och löses in i kassan. Kreditfakturor kan vara kreditfakturor för kredit eller returorder som utfärdats mot en returförsäljning. Om kreditfakturor bara löses in delvis utfärdar programmet en ny kreditfaktura med ett nytt saldo. Den nya kreditfakturan har ett nytt nummer. En kreditfaktura kan bara användas en gång och systemet håller reda på alla nummer som använts. Posten kan visas på sidan **Kreditfakturaregister**. Kunden kan inte lösa in mer än värdet på kreditfakturan.
-   **Presentkort** – Presentkort som utfärdas och löses in i kassan. Överbetalning är inte tillåten med presentkort.
-   **Kundkonto** – Betalningen kan debiteras ett kundkonto från kassan samtidigt som försäljningen. Du kan också använda denna betalningsmetod för att samla in försäljninginformation eller kundspecifika rabatter, eller när kunden gör betalningar, med hjälp av en annan betalningsmetod. I detta fall måste du ställa in kundspecifik information.
-   **Förmånspoäng** – poängen som samlar in kunder under bonusprogram. Om du skapar bonusprogram kunder poäng och lösa in dem på olika sätt. Till exempel i vissa bonusprogram kan kunder lösa in förmånspoängen i form av en rabatt eller även använda dem som en betalningsform.

Om du vill ställa in betalningsmetoder i Butik och handel måste du göra följande.

1.  Ställ in betalningsmetoder för en organisation. Skapa de betalningsmetoder som har godkänts för hela organisationen.
2.  Skapa organisationsomfattande korttyper och kortnummer på företagsnivå. Om kreditkort eller betalkort godtas måste du skapa en betalningsmetod för kort och sedan skapa företagsnivå korttyper och kortnummer på företagsnivå.
3.  Ställ in betalningsmetod för butiken. Koppla betalningssätt till butikerna och ange de butiksspecifika inställningarna för varje betalningssätt.
4.  Ställa in betalningsmetoder för kortet för butiker. Slutföra kortinställningarna för alla kort betalningsmetoder som accepterar butiken.


