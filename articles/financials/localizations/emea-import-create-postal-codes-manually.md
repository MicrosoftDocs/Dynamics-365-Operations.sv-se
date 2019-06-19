---
title: Importera eller skapa postnummer manuellt
description: Det här ämnet beskriver hur du importerar och manuellt skapar postnummer i rätt format. Det här avsnittet innehåller information om funktioner som lagts till eller ändrats för Microsoft Dynamics 365 for Finance and Operations.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LogisticsAddressSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 29901
ms.search.region: Belgium, Netherlands, Sweden
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: db7090e47301aad9ab56a62efd807140db62ab3b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559651"
---
# <a name="import-or-manually-create-postal-codes"></a>Importera eller skapa postnummer manuellt

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver hur du importerar och manuellt skapar postnummer i rätt format. Det här avsnittet innehåller information om funktioner som lagts till eller ändrats för Microsoft Dynamics 365 for Finance and Operations. 

Genom importen kan du uppdatera postnummer för ett visst land/en viss region. Du kan också skapa postnummer manuellt.

## <a name="import-zippostal-codes"></a>Importera postnr
Du kan använda sidan **Importera postnummer** för att importera nya postnummer till Finance and Operations. När du importerar koderna ersätts befintliga postnummer och postkoder med det nya formatet, och alla nya nummer/koder läggs till.

I vissa länder måste du använda ramverket för datahantering för att importera koder, medan för andra länder bara den överförda filen krävs. Belgien, Nederländerna och Sverige kräver en fil att överföra.

> [!NOTE]
> -   För Belgien tillhandahåller det belgiska postverkets hemsida en officiell lista över postnumren och motsvarande ortsnamn. Importen stöder html-filformat.
> -   För Nederländerna tillhandahåller en tredjepartsorganisation den fil som innehåller postnummer. När importen har slutförts visas alla postnummer i formatet (NNNN AA).
> -   För Sverige finns Postnummerservice.se, som tillhandahåller två typer av filer: svenska postnummer och svenska adresser. Importen stöder textfilsformat för båda typer.


## <a name="create-zippostal-codes-manually"></a>Skapa postnummer/postkoder manuellt
I stället för att importera koder kan du använda sidan **Adressinställningar** för att manuellt lägga till nya postnummer.


