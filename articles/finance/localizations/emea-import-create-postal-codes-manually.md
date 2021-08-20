---
title: Importera eller skapa postnummer manuellt
description: Det här ämnet beskriver hur du importerar och manuellt skapar postnummer i rätt format.
author: EvgenyPopovMBS
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LogisticsAddressSetup
audience: Application User
ms.reviewer: kfend
ms.custom: 29901
ms.search.region: Belgium, Netherlands, Sweden
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d547b6cb199279b6e40e6d6cf005086d62386421945cbeb04a9cfc395a55f0fc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768249"
---
# <a name="import-or-manually-create-postal-codes"></a>Importera eller skapa postnummer manuellt

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver hur du importerar och manuellt skapar postnummer i rätt format. 

Genom importen kan du uppdatera postnummer för ett visst land/en viss region. Du kan också skapa postnummer manuellt.

## <a name="import-zippostal-codes"></a>Importera postnr
Du kan använda sidan **Importera postnummer** för att importera nya postnummer till Dynamics 365 Finance. När du importerar koderna ersätts befintliga postnummer och postkoder med det nya formatet, och alla nya nummer/koder läggs till.

I vissa länder måste du använda ramverket för datahantering för att importera koder, medan för andra länder bara den överförda filen krävs. Belgien, Nederländerna och Sverige kräver en fil att överföra.

> [!NOTE]
> -   För Belgien tillhandahåller det belgiska postverkets hemsida en officiell lista över postnumren och motsvarande ortsnamn. Importen stöder html-filformat.
> -   För Nederländerna tillhandahåller en tredjepartsorganisation den fil som innehåller postnummer. När importen har slutförts visas alla postnummer i formatet (NNNN AA).
> -   För Sverige finns Postnummerservice.se, som tillhandahåller två typer av filer: svenska postnummer och svenska adresser. Importen stöder textfilsformat för båda typer.


## <a name="create-zippostal-codes-manually"></a>Skapa postnummer/postkoder manuellt
I stället för att importera koder kan du använda sidan **Adressinställningar** för att manuellt lägga till nya postnummer.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]