---
title: Massimportera användare
description: Den här proceduren kan användas av systemadministratörer för att importera ett stort antal användare från Azure Active Directory.
author: maertenm
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7d8b55895c9dfaf1c69cd319697f1e0da5990daf
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144097"
---
# <a name="import-users-in-bulk"></a>Massimportera användare

[!include [banner](../../includes/banner.md)]

Den här proceduren kan användas av systemadministratörer för att importera ett stort antal användare från Azure Active Directory.


## <a name="run-as-a-batch-job"></a>Kör som ett batchjobb
1. Gå till Systemadministration > Användare > Användare.
2. Klicka på Batchimport.
3. Expandera avsnittet Kör i bakgrunden.
4. Välj Ja i fältet Batchbearbetning.
5. Skriv ett värde i fältet Uppgiftsbeskrivning.
6. Ange eller välj ett värde i fältet Batchgrupp.
    * Detta steg är valfritt.  
7. Välj Ja i fältet Privat.
    * Detta steg är valfritt.  
8. Välj Ja i fältet Kritiskt jobb.
    * Detta steg är valfritt.  
9. Välj ett alternativ i fältet Övervakningskategori.
10. Klicka på OK.

## <a name="run-in-a-sandbox-environment"></a>Kör i ett begränsat läge
1. Klicka på Batchimport.
2. Klicka på OK.

