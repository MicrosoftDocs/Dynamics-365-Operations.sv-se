---
title: Betalsätt
description: Varje betalningstyp som en återförsäljare godtar, måste konfigureras när systemet installeras. Det här avsnittet ger en beskrivning av betalningstyperna som du kan ställa in och processen för hur du ställer in dem.
author: BrianShook
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: brshoo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.industry: Retail
ms.search.form: RetailTenderTypeTable
ms.openlocfilehash: d16cdf237042471d367adb7081bf34e9c8a9460f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272833"
---
# <a name="payment-methods"></a>Betalsätt

[!include [banner](includes/banner.md)]

Varje betalningstyp som en återförsäljare godtar, måste konfigureras när systemet installeras. Det här avsnittet ger en beskrivning av betalningstyperna som du kan ställa in och processen för hur du ställer in dem.

Återförsäljare kan acceptera olika typer av betalning i utbytet för produkter och tjänster som de säljer. Även om kontanter är den vanligaste betalningsformen kan också återförsäljare ta emot betalning i form av checkar, kort, verifikationer, osv. Varje betalningstyp som en återförsäljare godtar, måste konfigureras i Dynamics 365 Commerce när systemet installeras. I listan nedan beskrivs varje betalningstyp som kan ställas in:

- **Kontant** – Pengar i valutans fysiska form, som sedlar och mynt. Denna valuta kan antingen vara företagsvalutan eller butikens lokala valuta.
- **Check** – Ett överlåtbart instrument som ger instruktioner om betalning av ett specifikt belopp i en specifik valuta och som är utställt på en specifik bank. En check är vanligtvis giltig utan tidsgräns eller i sex månader efter utfärdandet, om inte en annan giltighetsperiod anges. Denna period, varierar beroende på banken som checken ställs ut på. Det finns olika typer av checkar, som ordercheckar, kassacheckar, innehavarcheckar och korsade checkar. Du kan ställa in checkar som ett betalsätt för varje butik. Checkar kan accepteras i den valuta som definieras på antingen företagsnivå eller butiksnivån. Du måste ställa in checkar som ett betalsätt, innan du kan acceptera en check som betalning i en butik.
- **Valuta** – Den primära formen av betalningsmedel förutom företagets standardvaluta. Mynt och sedlar är två former av valuta. Valutabetalsättet representerar alla valutor som används. Innan du kan använda den här typen av betalningsmedel måste du ställa in valutor och ange valutakurser för valutorna.
- **Kort** – Alla typer av kort som används, till exempel debetkort och kreditkort. Det är en bra idé att ställa in en kortbetalningsmetod på organisationsnivå för varje typ av kort. Sedan kan en typ av betalningsmetod ställas in för varje kort eller kortuppsättning på butiksnivå som bearbetas med samma inställningar. För att kunna använda typen av betalningsmedel Kort måste du ställa in de kort som finns på marknaden, dvs. betal- och kreditkort som Visa, Master och Euro, innan de kan godkännas som betalning i en butik.
- **Kreditfaktura** – Kreditfakturor som utfärdas och löses in i POS. Kreditfakturor kan vara kreditfakturor för kredit eller returorder som utfärdats mot en returförsäljning. Om kreditfakturor bara löses in delvis utfärdar programmet en ny kreditfaktura med ett nytt saldo. Den nya kreditfakturan har ett nytt nummer. En kreditfaktura kan bara användas en gång och systemet håller reda på alla nummer som använts. Posten kan visas på sidan **Kreditfakturaregister**. Kunden kan inte lösa in mer än värdet på kreditfakturan.
- **Presentkort** – Presentkort som utfärdas och löses in i POS. Överbetalning är inte tillåten med presentkort. Alla presentkort bör ha mappningar av kortnummer. 
- **Kundkonto** – Betalningen kan debiteras ett kundkonto från POS samtidigt som försäljningen. Du kan också använda denna betalningsmetod för att samla in försäljninginformation eller kundspecifika rabatter, eller när kunden gör betalningar, med hjälp av en annan betalningsmetod. I detta fall måste du ställa in kundspecifik information.
- **Förmånspoäng** – Poängen som kunder samlar in via bonusprogram. Om du skapar bonusprogram kan kunder tjäna in poäng och lösa in dem på olika sätt. Till exempel i vissa bonusprogram kan kunder lösa in förmånspoängen i form av en rabatt eller även använda dem som en betalningsform.

Om du vill ställa in betalsätten måste du göra följande.

1. Ställ in betalsätt för en organisation. Skapa de betalsätt som har godkänts för hela organisationen.
2. Skapa korttyper och kortnummer för hela organisationen. Om kreditkort eller betalkort tas emot måste du först skapa ett betalsätt för kort, och sedan skapa korttyper och kortnummer för hela organisationen.
3. Ställ in betalningsmetod för butiken. Associera betalsätten med varje butiker och ange sedan de butiksspecifika inställningarna för varje betalningsmetod.
4. Ställ in kortbetalsätt för butiker. Slutför kortinställningarna för alla kortbetalsätt som butiken godtar.

## <a name="handle-change-tendering-for-payment-methods"></a>Hantera ändringsofferter för betalningsmetoder

Vissa betalningsmetoder stöder inte direkta ändringsofferter om medel förs tillbaka till kunder vid kassan. Endast betalningsmetoderna **Kontant** och **Valuta** kan användas för ändringa ri betalningsmedel. 

Om du vill hantera de fall där betalningsmedel för växel krävs under en transaktion, men där betalningsmetoden inte stöder detta, kan du definiera en betalningsmetod för **betalningsmedel för växel**. När du ställer in betalningsmetoder för butiken väljer du den betalningsmetod som ska användas. I avsnittet **Växel**, i fältet **Betalningsmedel för växel**, anger du ett betalningsalternativ för betalningsmedel för växel. Du kan till exempel ange **1** om du vill ange att kontanter kan användas som ett alternativ för betalningsmedel för växel.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
