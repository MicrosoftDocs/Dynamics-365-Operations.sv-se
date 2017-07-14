---
title: Importera eller skapa postnummer manuellt
description: "Den här artikeln beskriver hur du importerar och manuellt skapar postnummer i rätt format. Det här avsnittet innehåller information om funktioner som har lagts till för Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LogisticsAddressSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 29901
ms.search.region: Belgium, Netherlands, Sweden
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 34dbdf5fe0d15069607a9f6154443684d59f6c1d
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Importera eller skapa postnummer manuellt
<a id="import-or-manually-create-postal-codes" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver hur du importerar och manuellt skapar postnummer i rätt format. Det här avsnittet innehåller information om funktioner som har lagts till för Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. 

Genom importen kan du uppdatera postnummer för ett visst land/en viss region. Du kan också skapa postnummer manuellt.

## Importera postnr
<a id="import-zippostal-codes" class="xliff"></a>
Du kan använda sidan **Importera postnummer** för att importera nya postnummer till Finance and Operations. När du importerar koderna ersätts befintliga postnummer och postkoder med det nya formatet, och alla nya nummer/koder läggs till.

I vissa länder måste du använda ramverket för datahantering för att importera koder, medan för andra länder bara den överförda filen krävs. Belgien, Nederländerna och Sverige kräver en fil att överföra.

> [!NOTE]
> -   För Belgien tillhandahåller det belgiska postverkets hemsida en officiell lista över postnumren och motsvarande ortsnamn. Importen stöder html-filformat.
> -   För Nederländerna tillhandahåller en tredjepartsorganisation den fil som innehåller postnummer. När importen har slutförts visas alla postnummer i formatet (NNNN AA).
> -   För Sverige finns Postnummerservice.se, som tillhandahåller två typer av filer: svenska postnummer och svenska adresser. Importen stöder textfilsformat för båda typer.


## Skapa postnummer/postkoder manuellt
<a id="create-zippostal-codes-manually" class="xliff"></a>
I stället för att importera koder kan du använda sidan **Adressinställningar** för att manuellt lägga till nya postnummer.



