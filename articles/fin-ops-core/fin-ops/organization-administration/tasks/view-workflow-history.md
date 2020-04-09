---
title: Visa arbetsflödeshistorik
description: Det här avsnittet beskriver steg för att visa statusvärdet för ett dokument som har skickats till arbetsflödessystemet för bearbetning och godkännande.
author: jasongre
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd5b8d9f3fd2edab50b52a8345f254ebc6b31d0a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140408"
---
# <a name="view-workflow-history"></a>Visa arbetsflödeshistorik

[!include [banner](../../includes/banner.md)]

Det här avsnittet beskriver steg för att visa statusvärdet för ett dokument som har skickats till arbetsflödessystemet för bearbetning och godkännande. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

1. Gå till **Navigeringsfönstret > Moduler > Allmänt > Förfrågningar > Arbetsflöde > Arbetsflödeshistorik**.
    - Använd det här formuläret för att visa statusvärdet för ett dokument som har skickats till arbetsflödessystemet för bearbetning och godkännande.  
    - **Instans-ID** är identifieringskoden för det arbetsflödesinstansen där dokumentet bearbetas eller har bearbetats.  
    - **Statusen** utgörs av dokumentets arbetsflödestatus.  
    - **ID för arbetsflöde** är identifieringskoden för det arbetsflöde där dokumentet bearbetas eller har bearbetats.  
    - **Dokumentet** är dokumentets identifieringskod.  
    - **Dokumenttypen** är den typ av dokument som har skickats in för bearbetning.  
    - **Arbetsflödet** är namnet på det arbetsflöde där dokumenten bearbetas eller har bearbetats.  
    - **Versionen** är versionsnumret på det arbetsflöde där dokumentet bearbetas eller har bearbetats.  
    - **Skapat datum och tid** är det datum och den tidpunkt då dokumentet skickades.  
    - **Förfluten tid** är den tid som har förflutit sedan dokumentet skickades.  
    - Knappen **Återuppta** låter dig fortsätta arbetsflödesprocessen för det valda dokumentet.  
    - Med knappen **Återkalla** kan du återkalla det markerade dokumentet så att det inte behandlas.   
2. Klicka på länken på önskad rad i listan.
    - Kontrollera att avsnittet för **Arbetsuppgifter** expanderas. I det här avsnittet kan du visa arbetsuppgifter som är kopplade till det valda dokumentet. En uppgift kan till exempel behöva slutföras, eller också kanske dokumentet måste godkännas.  
    - Knappen **Tilldela om** öppnar en dialogruta där du kan tilldela en arbetsuppgift till en annan användare.  
    - Kontrollera att avsnittet **Spårningsuppgifter** expanderas. I det här avsnittet kan du visa arbetsflödeshistoriken för det valda dokumentet.  

