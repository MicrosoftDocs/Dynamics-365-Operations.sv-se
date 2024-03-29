---
title: Infokoder och infokodgrupper
description: Den här artikeln ger en översikt över informationskoder och infokodgrupper och hur du använder dem.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 22761
ms.assetid: 99877dba-a6e3-4d88-ba0a-ee5913aea17e
ms.search.industry: Retail
ms.search.form: RetailInfocodeTable
ms.openlocfilehash: a6fc84db368c602f74778eb0a44ac52798dc5161
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273514"
---
# <a name="info-codes-and-info-code-groups"></a>Infokoder och infokodgrupper

[!include [banner](includes/banner.md)]

Den här artikeln ger en översikt över informationskoder och infokodgrupper och hur du använder dem.

Informationskoder utgör ett sätt att samla in data vid ett kassaregister (POS). Du kan använda informationskoder om du vill uppmana kassören att ange information under olika åtgärder i POS, till exempel artikelförsäljningar, artikelreturer eller val av kunder. Kassörer kan välja indata från en lista eller ange dem som en kod, ett nummer, ett datum eller text. Du kan tilldela infokoder till fördefinierade butiksåtgärder, butiksartiklar, betalsätt, kunder eller specifika kassaaktiviteter. Du kan använda informationskoder för att göra följande:

- Registrera ytterligare information vid tidpunkten för transaktionen, till exempel ett flygnummer eller orsaken till en retur.
- Låt kassaapparen välja från en lista med priser för specifika produkter.
- Länka en delkod till en informationskod för att uppmana kassören att ange indata när en viss aktivitet utförs. När en kund till exempel returnerar en produkt kan du uppmana kassören att undersöka varför produkten returneras. Därefter kan du använda delkoder för att visa en lista över orsaker som kassören kan välja från.
- Sälja en produkt som vanlig försäljning, rabatterad försäljning eller kostnadsfri produkt.
- Uppmana kassören att ange ett värde eller välja från en lista över delkoder när registerlådan öppnas utan att utföra en försäljningsoperation.

## <a name="info-codes-group"></a>Infokodgrupp

I Commerce kan du skapa grupper av informationskoder. Informationskodgrupper tillför flexibilitet genom att du kan definiera färre informationskoder och sedan använda dem på ett mer mångsidigt sätt. Du kan använda informationskodgrupper på följande sätt:

- Definiera färre informationskoder och återanvänd dem enkelt. Informationskoder som ingår i informationskodgrupper har inga fördefinierade beroenden i andra informationskoder. Du kan ta med samma informationskod i flera informationskodgrupper och sedan använda prioritering för att visa samma informationskoder i den ordning som fungerar för olika situationer.
- Länka infokoder till andra infokoder eller infokodgrupper för att samla in information om en produkt eller en transaktion så att du inte behöver ange en separat infokod eller den kopplade infokoden för alla scenarier.

## <a name="info-code-examples"></a>Exempel på infokod

**Exempel 1: Återanvända infokoder**

Du kan koppla infokoder så att, när en infokod utlöses, utlöses även en annan infokod omedelbart efter den. När du till exempel säljer vissa produkter kan du uppmana kassören att fråga kunden om de vill köpa batterier och en produktgaranti. För andra produkter kan du uppmana kassören att fråga kunden om de vill köpa batterier och för att hämta in deras postnummer. Om du skapar kopplade informationkoder för dessa situationer, måste du ställa in varje variant av informationskoden, så att kassapersonalen uppmanas att fråga efter den rätta informationen. Om du använder infokodgrupper kan du ställa in vanliga infokoder, till exempel frågor om batterier, en gång och sedan återanvända dem i flera infokodgrupper. Du kan också använda prioritering i informationkodgrupperna för att identifiera vilken ordning som visas prompten i.

**Exempel 2: Länka infokoder till  infokodgrupper**

När du säljer vissa produkter, till exempel mobila enheter, vill du alltid samla in specifik information, till exempel telefonnummer, den mobila utrustningsidentifieraren (MEID) och serienummer. Men du vill också hämta in olika information för en Tablet PC kontra en mobiltelefon. Du kan ställa in en informationkodgrupp som innehåller prompt för telefonnummer, MEID och serienummer och sedan informationkodgruppen länkar till en enskild informationskod. När den produktspecifika informationskoden utlöses, kan informationskodgruppen sedan utlösas för att göra det möjligt för dig att samla in gemensamma data, utan att behöva definiera flera uppsättningar av kopplade informationskoder för varje enhet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
