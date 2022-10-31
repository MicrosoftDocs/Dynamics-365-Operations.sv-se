---
title: Prestandaförbättring för aktivering av kontostruktur
description: Den här artikeln beskriver den nya prestandaförbättringen för aktiveringsprocessen för kontostruktur.
author: RyanCCarlson2
ms.date: 10/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-10-08
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 42f8fcebba6465261489f74a9bb1dd46c2d5fa16
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2022
ms.locfileid: "9714012"
---
# <a name="account-structure-activation-performance-enhancement"></a>Prestandaförbättring för aktivering av kontostruktur

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Med denna prestandaförbättring kan du aktivera kontostrukturerna snabbare genom att köra flera transaktionsuppdateringar samtidigt. Strukturen markeras dessutom som aktiv efter att den har validerats och transaktionsbearbetningen kan fortsätta medan befintliga, ej bokförda transaktioner uppdateras till den nya strukturen. Eftersom det kan ta en stund att uppdatera transaktioner kan du spåra statusen för din aktivering genom att välja **Visa aktiveringsstatus** ovanför rutnätet på sidan **Kontostrukturer**. Du kan också visa aktiveringsstatusen genom att välja **Visa** i åtgärdsfönstret och sedan välja **Aktiveringsstatus** i listrutan.

[![Sidan Kontostrukturer.](./media/AccountStructure1.png)](./media/AccountStructure1.png)

När du har valt **Visa aktiveringsstatus** visas en dialogruta som visar vilka enskilda uppgifter som körs under aktiveringsprocessen. För varje uppgift kan du visa status och, när uppgiften är slutförd, slutförandedatum och -tid.

[![Tidslinje för aktivering av kontostruktur.](./media/AccountStructureTimeline.png)](./media/AccountStructureTimeline.png)

## <a name="account-structure-activation-tips"></a>Tips för aktivering av kontostruktur

Dialogrutan för aktivering av kontostruktur som visas när du väljer **Aktivera** för en utkastkontostruktur finns i ett flikavsnitt med namnet **Uppdatera ej bokförda transaktioner**. Det här avsnittet innehåller ett alternativ som heter **Tvinga uppdatering**. Du kan välja det här alternativet om du vill uppdatera alla ej bokförda transaktioner till den aktuella strukturen. Du ska dock bara använda det här alternativet när ett fel har inträffat eller när Microsoft Support har hänvisat dig till att använda det.

Här är några av de faktorer som kan påverka prestandan under aktiveringsprocessen:

- Ett stort antal ej bokförda journalposter
- Ett stort antal öppna källdokumentposter, t.ex. fritextfakturor, leverantörsfakturor och relaterade dokument som använder källdokumentramverket och har öppna redovisningsfördelningar.
- Mängden data i TaxUncommitted
- Mängden öppna budgetdata
- Import av journaldata när aktiveringsuppgifterna fortfarande körs

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
