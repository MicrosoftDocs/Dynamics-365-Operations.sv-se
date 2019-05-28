---
title: Importera valutakurser
description: Om en juridisk person har fått fakturor i utländsk valuta, måste den utländska valutan konverteras till lokal valuta. Detta innebär att aktuella valutakurser krävs för olika valutor. Det här avsnittet innehåller en översikt över de inställningar och den bearbetning som krävs för att importera utländska referensvalutakurser som publiceras online av valutakursleverantörer som exempelvis Europeiska centralbanken och Ryska centralbanken.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: edd72b48a640126577dd7a2add3a4891ae505fdf
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557972"
---
# <a name="import-currency-exchange-rates"></a>Importera valutakurser

[!include [banner](../includes/banner.md)]

Om en juridisk person har fått fakturor i utländsk valuta, måste den utländska valutan konverteras till lokal valuta. Detta innebär att aktuella valutakurser krävs för olika valutor. Det här avsnittet innehåller en översikt över de inställningar och den bearbetning som krävs för att importera utländska referensvalutakurser som publiceras online av valutakursleverantörer som exempelvis Europeiska centralbanken och Ryska centralbanken.

Följande avsnitt beskriver det allmänna informationsflödet som används för att konfigurera och bearbeta importen av utländska valutakurser.

## <a name="configure-an-exchange-rate-provider"></a>Ställ in en valutakursleverantör
Innan du kan importera valutakurser måste du ställa in den information som krävs av de leverantörer som erbjuder valutakurser. Använd sidan **Konfigurera valutakursleverantörer** för att välja valutakursleverantörer. Vissa valutakursleverantörer medföljer demonstrationsdatan i Microsoft Dynamics 365 for Finance and Operations. I följande tabell finns beskrivningar av kontrollerna på denna sida.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Fält** | **Beskrivning**                                                                                                                                                                                                             |
| **Namn**  | Valutakursleverantörens namn.                                                                                                                                                                                     |
| **Nyckel**   | Det unika id:t för varje konfigurationsuppgift som krävs av leverantören. Den här informationen läggs till automatiskt för varje valutakursleverantör som du lägger till genom att klicka på knappen **Lägg till**. |
| **Värde** | Information för varje nyckel. Den här informationen läggs till för varje valutakursleverantör som du lägger till genom att klicka på knappen **Lägg till**.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importera valutakurser
Du kan importera valutakurser från valutakursleverantörskällan och ställa in dem på sidan **Valutakurser**. Använd sidan **Importera valutakurser** om du vill importera valutakurser. I följande tabell beskrivs de fält som krävs för att genomföra importen.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Fält**                              | **Beskrivning**                                                                                                                                                                                                                                                                                                                                                             |
| **Valutakurstyp**                 | En valutakurstyp.                                                                                                                                                                                                                                                                                                                                                      |
| **Valutakursleverantör**             | En valutakursleverantör.                                                                                                                                                                                                                                                                                                                                                  |
| **Importera från och med**                       | Denna parameter styr huruvida import ska ske från och med dagens datum eller för ett datumintervall. Ange start- och slutdatum för att använda ett visst datumintervall.                                                                                                                                                                                                                |
| **Skapa nödvändiga valutapar**    | Den här kryssrutan styr automatiskt skapande av valutapar, om de valutapar som importeras inte finns. Det här alternativet är kanske inte tillgängligt för vissa leverantörer.                                                                                                                                                                                               |
| **Ersätt befintliga valutakurser**   | Den här kryssrutan hanterar uppdateringen av den befintliga valutakursen för ett valutapar när valutakursen för ett visst datum redan finns. Om du inte markerar den här kryssrutan, importeras inte valutakursen för specifika datum om det redan finns en annan valutakurs.                                                                                       |
| **Förhindra import på helgdagar** | Den här kryssrutan styr importen av valutakurser för ett datum som är en helgdag. Om du till exempel markerar den här kryssrutan och använder Europeiska centralbanken som valutakursleverantör, uppdaterar systemet inte valutakursen på en allmän helgdag som hör till den aktuella juridiska personen. Det här alternativet är kanske inte tillgängligt för vissa leverantörer. |





