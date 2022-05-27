---
title: Affärsdokument som stöds av Global Lagerredovisning
description: Det här ämnet visar en lista med affärsdokument som stöds av Global lagerredovisning. Det ger också ett detaljerat exempel på inköpsorderdokument.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 44081be35c6737aa0d16b6e11a5fc8f94b41e872
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674461"
---
# <a name="business-documents-supported-by-global-inventory-accounting"></a>Affärsdokument som stöds av Global Lagerredovisning

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

När tillägget Global lagerredovisning är helt inställt kan det bearbeta lagerrelaterade dokument som anges i Microsoft Dynamics 365 Supply Chain Management.

## <a name="supported-business-documents"></a>Affärsdokument som stöds

Det finns två typer av affärsdokument:

- **Dokument som har en journal** – Dessa dokument inkluderar produktinleverans, inköpsfaktura, följesedel och försäljningsfakturadokument.
- **Dokument som inte har någon journal** – Dessa dokument inkluderar inventerings-, förflyttnings- och lagerjusteringsdokument.

Senare i det här avsnittet används inköpsorder som exempel för att illustrera processen.

I följande tabell visas de dokument som den aktuella versionen stöder.

| Dokumenttyp      | Dokument        |
|--------------------|-----------------|
| Inköpsorder     | Produktinleverans |
| Inköpsorder     | Faktura         |
| Försäljningsorder        | Följesedel    |
| Försäljningsorder        | Faktura         |
| Lagerjournaler | Rörelse        |
| Lagerjournaler | Justering      |
| Lagerjournaler | Inventering        |
| Lagerjournaler | Överför        |
| Överföringsorder     | Försändelse        |
| Överföringsorder     | Ta emot         |

> [!IMPORTANT]
> Global lagerredovisning bearbetar asynkront de dokument som anges i Supply Chain Management. Inga felmeddelanden visas för problematiska dokument.

## <a name="example-purchase-order"></a>Exempel: inköpsorder

### <a name="product-receipt"></a>Produktinleverans

Bokför produktinleveranser som vanligt. På sidan **Alla inköpsorder** välj en inköpsorder och sedan i åtgärdsfönstret på fliken **Mottagning** välj **Produktinleverans** för att öppna sidan **Produktinleveransjournal**. En operationshändelse och en global lagerredovisningshändelse skapas för varje rad. Därför väljer du fliken **Rader** och väljer **Lager \> Händelser och mätningar** för att öppna sidan **Händelser och mätningar**.

Global lagerredovisning är ett redovisningssystem som baseras på händelser och mätningar. Måttradrutnätet på sidan **Händelser och mätningar** visar en lista med mått. Varje mått har en lista över dimensioner.

För varje operationshändelse finns två typer av mätningar:

- **Operationsmått** – Dessa mått beskriver affärsdokument i allmänna termer. Ett mått är produktkvantiteten med hjälp av måttenheten som används i dokumentet. Det finns också mätningar som påverkar lagervärdet, till exempel utökat pris, rabatt, rabattprocent och radavgift.
- **Resursredovisningsmått** – Dessa mätningar kommer från lagerregisterperspektiv. De beskriver dokumentets inverkan på lagret i lagermåttet. Om det finns flera lagerregistreringar finns det flera rader med resursredovisningsmått.

Dimensionerna ordnas på följande sätt:

- **Dualitet** – Dualitet beskriver de ombud som deltar i de ekonomiska händelserna. För externa affärsdokument beskriver dimensionerna för den juridiska personen där dokumentet förs in, medan dimensionerna för beskriv leverantören, kunden och så vidare. För interna affärsdokument (till exempel överföringsorder) beskriver dimensionerna motsvarande lagerställe.
- **Dimensionstyp** – Dimensionstyper kategoriserar dimensionerna.
- **Dimension** – Namnet på dimensionen.
- **Dimensionsvärde** – Värdet på dimensionen.

### <a name="global-inventory-accounting-event"></a>Global lagerredovisningshändelse

I Global lagerredovisning sker drifthändelser och mätningar som indata. Därefter gör den lämpliga redovisningen för varje relaterad redovisning, baserad på den kopplade valutan och konventionen. Du kan välja **händelser och mått för global lagerredovisning** om du vill visa händelsen Global lagerredovisning. Händelsen global lagerredovisning följer samma metodik som operationshändelser, men använder olika mått. Det finns tre stora måtttyper: produktkostnadskvantitet, produktkostnad och avvikelse.

Delredovisningskonton används för att ytterligare klassificera mätningarna. Det kan finnas flera redovisningar. Dessa redovisningar är länkade till den juridiska person där dokumentet registreras. Du kan visa händelser och mått för varje redovisning genom att ändra värdet i fältet **redovisning**.

### <a name="cost-element"></a>Kostnadselement

Baserat på den kostnadselementpolicy som är kopplad till redovisningen tilldelar systemet ett kostnadselement till varje redovisad åtgärdshändelsemått som påverkar lagerkostnaden. Måtten omfattar utökat pris, rabatt, rabattprocent och radavgift.

### <a name="measurement-line-details"></a>Information om måttrad

På fliken **Översikt** visas information om de kopplade principerna. Kostnadsobjektdimensionerna visar kostnadsobjektet, baserat på kostnadsobjektpolicyn. Specifika identifieringsdimensioner visar batchnumret om kostnadsflödesantagandet är *Specifikt – Batch*.

### <a name="purchase-invoice"></a>Inköpsfaktura

Bokför fakturan som vanligt. I åtgärdsfönstret på fliken **Faktura** i gruppen **Journaler** väljer du sedan **Faktura** för att öppna fakturajournalen. En operationshändelse och en global lagerredovisningshändelse skapas för varje rad. Därför väljer du fliken **Rader** och väljer **Lager \> Händelser och mätningar** för att öppna sidan **Händelser och mätningar**. Sidan **Händelser och mått** visar samma måtttyp. Eftersom sidan visar en annan måttroll och måttmodifierare, skiljer sig dock effekten på agenten (den juridiska personen).

Du kan välja **händelser och mått för global lagerredovisning** om du vill visa händelsen Global lagerredovisning. Lagerkvantiteten och kostnaden kommer nu från redovisningskontot för *mottagna varor som inte fakturerats i lager* och till kontot för *kostnader för inköpta varor* i redovisningskontot.
