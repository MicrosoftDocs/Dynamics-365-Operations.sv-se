---
title: Instrumentpanel för användningshantering
description: I det här ämnet beskrivs hur du använder instrumentpanelen för användningshantering för att övervaka användningen av den elektroniska faktureringstjänsten och fortsatt efterleva standarder.
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 3fad2acea373e96092208ce06edb31f1a862912d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875983"
---
# <a name="usage-management-dashboard"></a>Instrumentpanel för användningshantering

[!include [banner](../includes/banner.md)]

Med hjälp av instrumentpanelen för **användarhantering** kan du övervaka användningen av den elektroniska faktureringstjänsten och på så sätt hjälpa organisationen att fortsatt efterleva standarder i fråga om dess månatliga användning. Efterlevnaden avgörs genom att beräkna insändningsvolymen och jämföra denna med den anskaffade insändningsvolymen i syfte att identifiera eventuella avvikelser mellan den anskaffade volymen och den använda volymen.

Instrumentpanelen innehåller följande indikatorer:

- En kostnadsindikator som du kan använda för att övervaka förbrukning i licensefterlevnadssyfte:

    - Användning per månad (export)

- Tre driftindikatorer som du kan använda för att spåra användningen av den elektroniska faktureringstjänsten i hanteringssyfte:

    - Användning per funktion
    - Användning per miljö
    - Användning per månad (import)

## <a name="measurement-scope"></a>Måttomfång

- Måttenhet: 

    Instrumentpanelen för **användarhantering** räknar sändningen av affärsdokument och importerade elektroniska fakturor.

- Organisation: 

    Inventeringen sammanfattas efter organisationens klientorganisations-ID, oavsett antalet instanser av Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management eller det antal juridiska personer där tjänsten för elektronisk fakturering har aktiverats.


## <a name="indicator-usage-per-month-export"></a>Indikator: Användning per månad (export)

Denna indikator ger information om de elektroniska fakturor som din organisation utfärdar under en angiven period.

### <a name="scope"></a>Omfattning
- Antalet affärsdokument som skickas från Finance och Supply Chain Management till den elektroniska faktureringstjänsten, oavsett antalet rader som dessa affärsdokument innehåller.
- Antalet skickade affärsdokument som har bearbetats av den elektroniska faktureringstjänsten. Ett dokument betraktas som färdigbearbetat när det åtgärdsflöde som har definierats i funktionsinställningarna har slutförts.

> [!NOTE]
> När en elektronisk faktura skickas till en extern webbtjänst är inventeringen oberoende av resultatet av webbtjänstbearbetningen (godkänd, avvisad eller schemavalideringsfel). Om webbtjänsten har tagits emot och svarat på en begäran från den elektroniska faktureringstjänsten betraktas sändningen som en giltig inventering.

- **Undantag:** Affärsdokument räknas inte om de skickas om från Finance och Supply Chain Management till den elektroniska faktureringstjänsten, t. ex. i de scenarier där en ny sändning av samma affärsdokument krävs för att ändra statusen för den elektroniska fakturan. Till exempel räknas utfärdandet av en elektronisk brasiliansk faktura (skattedokument) som giltigt, men annulleringsförfrågan för den räknas inte.


### <a name="calculation"></a>Beräkning

Beräkningen av saldot beräknas på följande sätt:

Saldo = Kostnadsfri + Inköpt – Används

Där:

- Kostnadsfritt:
  
    Ett kostnadsfritt antal affärsdokument som kunden kan skicka per månad. Detta omfattar ett paket om 100 affärsdokument som kan skickas till den elektroniska faktureringstjänsten. Den kostnadsfria volymen ackumuleras inte, och eventuella återstående saldon flyttas inte över till nästa period.
  
- Inköpt:
  
    Ett paket om 1 000 affärsdokument som kan skickas till den elektroniska faktureringstjänsten. Detta paket måste förvärvas för din organisation en gång i månaden. Inköpt volym ackumuleras inte, och eventuella återstående saldon flyttas inte över till nästa period.
  
- Används: 

    Antalet affärsdokument som skickas till den elektroniska faktureringstjänsten enligt definierade kriterier.
   
> [!IMPORTANT]
> Om din organisation tänker överskrida månadsvolymen på 100 gratisutskick ska du köpa in toppvolymen så att du förblir kompatibel med Microsofts licenspolicy för den elektroniska faktureringstjänsten.
>
> För närvarande måste inköpt volym anges manuellt, enligt anskaffningsdatum, som flera paket med 1 000 sändningar.

## <a name="indicator-usage-by-feature"></a>Indikator: Användning efter funktion

Denna indikator visar användningen av elektroniska faktureringsfunktioner för utfärdande av elektroniska fakturor under en angiven period.

- Beräkning:
  
    Använd = Räkningen av hur många gånger som respektive elektronisk faktureringsfunktion har använts under överföringen av affärsdokument till den elektroniska faktureringstjänsten.

## <a name="indicator-usage-by-environment"></a>Indikator: Användning efter miljö

Denna indikator visar användningen av miljöer för elektroniska faktureringstjänster under en angiven period.

- Beräkning:
    
    Använd = Räkningen av hur många gånger som respektive miljö för elektronisk faktureringstjänst har använts under överföringen av affärsdokument till den elektroniska faktureringstjänsten.

## <a name="indicator-usage-per-month-import"></a>Indikator: Användning per månad (import)

Denna indikator visar importvolymen för elektroniska fakturor för tjänsten för elektronisk fakturering till Finance och Supply Chain Mangement under en angiven period.

- Omfång:

    Elektroniska fakturor som importeras till Finance och Supply Chain Management, oavsett hur många rader de elektroniska fakturorna innehåller.

- Beräkning:

    Mottaget = Antalet importerade elektroniska fakturor till Finance och Supply Chain Management.

## <a name="functions"></a>Funktioner
### <a name="purchase"></a>Inköp

På fliken **Användning per månad (export)** väljer du **Inköp** om du vill registrera antalet anskaffade inskick manuellt.

För ett visst datum väljer du **Ny** och anger antalet **Paket** som förvärvats på det datumet.

**Kvantiteten** beräknas som:

Kvantitet = Paket * 1 000

Den beräknade **Kvantiteten** visas i **Inköpt** från indikatorn **Användning per månad (export)**.

### <a name="update"></a>Uppdatera

I åtgärdsfönstret väljer du **Uppdatera** för att uppdatera beräkningen och uppdatera de data som anges på sidan och i tabellen.

### <a name="reset-history-data"></a>Återställ historikdata

I åtgärdsfönstret väljer du **Återställ historikdata** för att uppdatera databasen där indikatorerna beräknas.




> [!NOTE]
> Instrumentpanelen **Användarhantering** visar inga monetära belopp. Istället visas bara volymen för räknade inskick och importerade dokument.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
