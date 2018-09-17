--- 
title: "Visa arbetsflödeshistorik"
description: "Använd följande steg för att visa statusvärdet för ett dokument som har skickats till arbetsflödessystemet för bearbetning och godkännande."
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 212f9fe8bc7807b9209523564ead716959875241
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="view-workflow-history"></a>Visa arbetsflödeshistorik

[!include [task guide banner](../../includes/task-guide-banner.md)]

Använd följande steg för att visa statusvärdet för ett dokument som har skickats till arbetsflödessystemet för bearbetning och godkännande. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

1. Gå till Allmänt > Förfrågningar > Arbetsflöde > Arbetsflödeshistorik.
    * Använd det här formuläret för att visa statusvärdet för ett dokument som har skickats till arbetsflödessystemet för bearbetning och godkännande.  
    * Instans-ID är identifieringskoden för det arbetsflödesinstansen där dokumentet bearbetas eller har bearbetats.  
    * Statusen utgörs av dokumentets arbetsflödessatus.  
    * ID för arbetsflöde är identifieringskoden för det arbetsflöde där dokumentet bearbetas eller har bearbetats.  
    * Dokumentets ID är dokumentets identifieringskod.  
    * Dokumenttypen är den typ av dokument som har skickats in för bearbetning.  
    * Arbetsflödet är namnet på det arbetsflöde där dokumenten bearbetas eller har bearbetats.  
    * Versionen är versionsnumret på det arbetsflöde där dokumentet bearbetas eller har bearbetats.  
    * Datum och tid för "Skapades den" är det datum och den tidpunkt då dokumentet skickades.  
    * Förfluten tid är den tid som har förflutit sedan dokumentet skickades.  
    * Knappen Återuppta låter dig fortsätta arbetsflödesprocessen för det valda dokumentet.  
    * Med knappen Återkalla kan du återkalla det markerade dokumentet så att det inte behandlas.   
2. Klicka på länken på den valda raden i listan.
    * Kontrollera att avsnittet för Arbetsuppgift expanderas.    I det här avsnittet kan du visa arbetsuppgifter som är kopplade till det valda dokumentet. En uppgift kan till exempel behöva slutföras, eller också kanske dokumentet måste godkännas.  
    * Knappen Överlåta öppnar en dialogruta där du kan tilldela en arbetsuppgift till en annan användare.  
    * Kontrollera att informationsavsnittet för spårning expanderas.    I det här avsnittet kan du visa arbetsflödeshistoriken för det valda dokumentet.  


