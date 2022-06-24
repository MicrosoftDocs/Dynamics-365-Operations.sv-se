---
title: Visa arbetsflödeshistorik
description: Den här artikeln beskriver steg för att visa statusvärdet för ett dokument som har skickats till arbetsflödessystemet för bearbetning och godkännande.
author: jasongre
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a5810eaed5d2ff6cb5c98e1b21c098c70f24485
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868591"
---
# <a name="view-workflow-history"></a>Visa arbetsflödeshistorik

[!include [banner](../../includes/banner.md)]


[!INCLUDE [PEAP](../../../../includes/peap-1.md)]

Den här artikeln beskriver steg för att visa statusvärdet för ett dokument som har skickats till arbetsflödessystemet för bearbetning och godkännande. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

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



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]