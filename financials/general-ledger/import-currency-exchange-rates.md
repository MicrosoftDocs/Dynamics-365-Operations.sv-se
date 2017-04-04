---
title: Importera valutakurser
description: "Om en juridisk person har fått fakturor i utländsk valuta, behöver den utländska valutan konverteras till basvalutan. Detta innebär att aktuell valutakurser olika krävs. Det här avsnittet innehåller en översikt över nödvändiga inställningar och bearbetning för att importera referens valutakurser publicerad begärd av valutakursleverantörer som Europeiska centralbanken tillämpar och Ryssland centralbanken."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf66a1b1c9314b454223274810a21913d54b702d
ms.lasthandoff: 03/31/2017


---

# <a name="import-currency-exchange-rates"></a>Importera valutakurser

Om en juridisk person har fått fakturor i utländsk valuta, behöver den utländska valutan konverteras till basvalutan. Detta innebär att aktuell valutakurser olika krävs. Det här avsnittet innehåller en översikt över nödvändiga inställningar och bearbetning för att importera referens valutakurser publicerad begärd av valutakursleverantörer som Europeiska centralbanken tillämpar och Ryssland centralbanken.

I följande avsnitt beskrivs informationsflödet som används för att skapa och bearbeta importen av valutakurser.

## <a name="configure-an-exchange-rate-provider"></a>Konfigurera en valutakursleverantör
Innan du kan importera valutakurser, måste du ställa in den information som krävs enligt vilka leverantörer som erbjuder valutakurser. Använd den **konfigurera valutakursleverantörer** att välja vilka valutakursleverantörer. Vissa valutakursleverantörer medföljer demonstrationsdata i Microsoft Dynamics 365 för operationer. Nedan visas beskrivningar av kontrollerna på den här sidan.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field** | **Description**                                                                                                                                                                                                             |
| **Name**  | Valutakursleverantörens namn.                                                                                                                                                                                     |
| **Nyckeln**   | Det unika id:t för varje konfigurationsuppgift som krävs av leverantören. Den här informationen läggs automatiskt för varje valutakursleverantör som du lägger till när du klickar på de **Lägg** knappen. |
| **Value** | Information för varje nyckel. Informationen läggs till för varje valutakursleverantör som du lägger till när du klickar på de **Lägg** knappen.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importera valutakurser
Du kan importera valutakurser från leverantörer valutakurs som källa och ställer in dem i den **valutakurser** sida. Använd den **importera valutakurser** om du vill importera valutakurser. I följande tabell beskrivs de fält som krävs för att genomföra importen.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field**                              | **Description**                                                                                                                                                                                                                                                                                                                                                             |
| **Exchange rate type**                 | En valutakurstyp.                                                                                                                                                                                                                                                                                                                                                      |
| **Exchange rate provider**             | En valutakursleverantör.                                                                                                                                                                                                                                                                                                                                                  |
| **Import as of**                       | Det hanterar den här parametern om du vill importera från och med dagens datum eller ett datumintervall. Ange eller välj start- och slutdatum om du vill använda ett visst datumintervall.                                                                                                                                                                                                                |
| **Create necessary currency pairs**    | Den här kryssrutan om hanterar automatiskt skapande av valutapar, om valutapar som importeras inte finns. Det här alternativet är kanske inte tillgängliga för vissa leverantörer.                                                                                                                                                                                               |
| **Override existing exchange rates**   | Den här kryssrutan om hanterar uppdateringen av befintliga valutakursen för ett valutapar när valutakursen för ett visst datum som redan finns. Om du inte markerar den här kryssrutan importeras inte valutakursen för specifika datum om det redan finns en annan valutakursen.                                                                                       |
| **Prevent import on national holiday** | Den här kryssrutan om hanterar importen av valutakursen för ett datum som är en helgdag. Till exempel om du markerar den här kryssrutan och använda Europeiska centralbanken som vilken valutakursleverantör uppdateras systemet inte valutakursen på en allmän helgdag som hör till den aktuella juridiska personen. Det här alternativet är kanske inte tillgängliga för vissa leverantörer. |




