---
title: Importera valutakurser
description: Den här artikeln innehåller information om kraven för att importera referensvalutakurser för utländsk valuta som publiceras av valutakursleverantörer.
author: EvgenyPopovMBS
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 27f9b06646d9ce948a6b4528c38c5df9784b24b2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894947"
---
# <a name="import-currency-exchange-rates"></a>Importera valutakurser

[!include [banner](../includes/banner.md)]

Om en juridisk person har fått fakturor i utländsk valuta, måste den utländska valutan konverteras till lokal valuta. Detta innebär att aktuella valutakurser krävs för olika valutor. Den här artikeln innehåller en översikt över de inställningar och den bearbetning som krävs för att importera utländska referensvalutakurser som publiceras av valutakursleverantörer som exempelvis Europeiska centralbanken och Ryska centralbanken.

Följande avsnitt beskriver det allmänna informationsflödet som används för att konfigurera och bearbeta importen av utländska valutakurser.

## <a name="configure-an-exchange-rate-provider"></a>Ställ in en valutakursleverantör
Innan du kan importera valutakurser måste du ställa in den information som krävs av de leverantörer som erbjuder valutakurser. Använd sidan **Konfigurera valutakursleverantörer** för att välja valutakursleverantörer. Vissa valutakursleverantörer medföljer demonstrationsdatan i Dynamics 365 Finance. I följande tabell finns beskrivningar av kontrollerna på denna sida.

| Fält | beskrivning                   |
|-----------|-----------------------------------|
| **Namn**  | Valutakursleverantörens namn.                                                                                                                                                                                     |
| **Nyckel**   | Det unika id:t för varje konfigurationsuppgift som krävs av leverantören. Den här informationen läggs till automatiskt för varje valutakursleverantör som du lägger till. |
| **Value** | Information för varje nyckel. Den här informationen läggs till för varje valutakursleverantör som du lägger till.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importera valutakurser
Du kan importera valutakurser från valutakursleverantörskällan och lägga till dem på sidan **Valutakurser**. Använd sidan **Importera valutakurser** om du vill importera valutakurser. I följande tabell beskrivs de fält som krävs för att genomföra importen.

| Fält | beskrivning                   |
|-----------|-----------------------------------|
| **Valutakurstyp**                 | En valutakurstyp.                                                                                                                                                                                                                                                                                                                                                      |
| **Valutakursleverantör**             | En valutakursleverantör.                                                                                                                                                                                                                                                                                                                                                  |
| **Importera från**                       | Denna parameter styr huruvida import ska ske från och med aktuellt datum eller för ett specifikt datumintervall. Ange start- och slutdatum för att använda eller välja start- och slutdatum.                                                                                                                                                                                                                |
| **Skapa nödvändiga valutapar**    | Den här kryssrutan styr automatiskt skapande av valutapar, om de valutapar som importeras inte finns. Det här alternativet är kanske inte tillgängligt för vissa leverantörer.                                                                                                                                                                                               |
| **Ersätt befintliga valutakurser**   | Den här kryssrutan hanterar uppdateringen av den befintliga valutakursen för ett valutapar när valutakursen för ett visst datum redan finns. Om du inte markerar den här kryssrutan, importeras inte valutakursen för specifika datum om det redan finns en annan valutakurs.                                                                                       |
| **Förhindra import på helgdagar** | Den här kryssrutan styr importen av valutakurser för en helgdag. Om du till exempel markerar den här kryssrutan och använder Europeiska centralbanken som valutakursleverantör, uppdaterar systemet inte valutakursen på en allmän helgdag som hör till den aktuella juridiska personen. Det här alternativet är kanske inte tillgängligt för vissa leverantörer. |
| **Kurs från föregående dag** | Den här kryssrutan är tillgänglig om du aktiverar **ECB-import på det aktuella eller föregående datum** på sidan **funktionshantering**. Den här kryssrutan är bara tillgänglig för leverantören, *centralbanken i Europa*. Markera den här kryssrutan om du vill importera den valutakurs som publicerats av europeiska centralbanken föregående arbetsdag cirka 16:00. Kryssrutan är markerad som standard. Avmarkera den här kryssrutan om du vill importera den valutakurs som har publicerats på samma arbetsdag.  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]