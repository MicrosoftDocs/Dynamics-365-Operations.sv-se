---
title: Importera eller manuellt skapa postnummer
description: "Den här artikeln beskrivs hur du importerar och manuellt skapa postnummer i rätt format. Det här avsnittet innehåller information om funktioner som har lagts till för Microsoft Dynamics 365 för operationer."
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

# <a name="import-or-manually-create-postal-codes"></a>Importera eller manuellt skapa postnummer

Den här artikeln beskrivs hur du importerar och manuellt skapa postnummer i rätt format. Det här avsnittet innehåller information om funktioner som har lagts till för Microsoft Dynamics 365 för operationer. 

Importen kan du uppdatera postnummer för ett visst land/region. Du kan skapa postnummer manuellt.

## <a name="import-zippostal-codes"></a>Importera postnr
Du kan använda den **importera postnummer** sidan Importera nya postnummer till Microsoft Dynamics 365 för operationer. När du importerar koderna befintliga postnummer och postkoder ersätts med det nya formatet och läggs alla nya koder.

I vissa länder, måste du använda Data management framework importera koderna, medan andra länder krävs bara den överförda filen. Belgien, Nederländerna och Sverige måste filen som ska överföras.

> [!NOTE]
> -   Belgien ger en officiell förteckning av postcodes och motsvarande ortsnamnet officiella webbsida från belgiska inlägget. Importen stöder html-format.
> -   Nederländerna är en tredje parts den fil som innehåller postnummer. När importen har slutförts visas alla postnummer i formatet (NNNN AA).
> -   Postnummerservice.se för Sverige, innehåller två typer av filer: svenska postnummer och svenska adresser. Importen stöder textformat för båda typerna.


## <a name="create-zippostal-codes-manually"></a>Skapa postnummer manuellt
I stället för import av koder som du kan använda den **adressinställning** sida manuellt lägga till nya postnummer.

