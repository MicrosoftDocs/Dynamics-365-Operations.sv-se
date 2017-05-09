---
title: Importera eller skapa postnummer manuellt
description: "Den här artikeln beskriver hur du importerar och manuellt skapar postnummer i rätt format. Det här avsnittet innehåller information om funktioner som har lagts till för Microsoft Dynamics 365 for Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LogisticsAddressSetup
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 29901
ms.assetid: 0c9cbc5f-88ae-4ed2-8331-13ecea029f79
ms.search.region: Belgium, Netherlands, Sweden
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 700a4aec4d89fc9e99e9570c409a7a9b3a6be2c5
ms.lasthandoff: 03/31/2017


---

# <a name="import-or-manually-create-postal-codes"></a>Importera eller skapa postnummer manuellt

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver hur du importerar och manuellt skapar postnummer i rätt format. Det här avsnittet innehåller information om funktioner som har lagts till för Microsoft Dynamics 365 for Operations. 

Genom importen kan du uppdatera postnummer för ett visst land/en viss region. Du kan också skapa postnummer manuellt.

## <a name="import-zippostal-codes"></a>Importera postnr
Du kan använda sidan **Importera postnummer** för att importera nya postnummer till Microsoft Dynamics 365 for Operations. När du importerar koderna ersätts befintliga postnummer och postkoder med det nya formatet, och alla nya nummer/koder läggs till.

I vissa länder måste du använda ramverket för datahantering för att importera koder, medan för andra länder bara den överförda filen krävs. Belgien, Nederländerna och Sverige kräver en fil att överföra.

> [!NOTE]
> -   För Belgien tillhandahåller det belgiska postverkets hemsida en officiell lista över postnumren och motsvarande ortsnamn. Importen stöder html-filformat.
> -   För Nederländerna tillhandahåller en tredjepartsorganisation den fil som innehåller postnummer. När importen har slutförts visas alla postnummer i formatet (NNNN AA).
> -   För Sverige finns Postnummerservice.se, som tillhandahåller två typer av filer: svenska postnummer och svenska adresser. Importen stöder textfilsformat för båda typer.


## <a name="create-zippostal-codes-manually"></a>Skapa postnummer/postkoder manuellt
I stället för att importera koder kan du använda sidan **Adressinställningar** för att manuellt lägga till nya postnummer.



