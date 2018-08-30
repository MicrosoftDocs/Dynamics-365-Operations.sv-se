--- 
title: "Konfigurera systemet för att skicka arbetsflödesrelaterad e-post till användare"
description: "Du kan konfigurera systemet till att skicka e-postmeddelanden till användare vid arbetsflödesrelaterade händelser."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 04d90c9ded1ba7fb1ceac4ff1d54f54f6c43f9e9
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="configure-the-system-to-send-workflow-related-email-to-users"></a>Konfigurera systemet för att skicka arbetsflödesrelaterad e-post till användare

[!include [task guide banner](../../includes/task-guide-banner.md)]

Du kan konfigurera systemet till att skicka e-postmeddelanden till användare vid arbetsflödesrelaterade händelser. E-postmeddelanden kan till exempel skickas till användare när dokument tilldelas till dem för godkännande. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

1. Gå till Systemadministration > Användare > Användare.
2. Hitta och markera önskad post i listan.
3. Klicka på Användaralternativ.
4. Klicka på fliken Arbetsflöde.
    * Kontrollera att avsnittet för meddelanden expanderas.     I avsnittet för meddelanden kan du ange hur du vill att användaren ska meddelas om arbetsflödesrelaterade händelser.  
5. Välj ett alternativ i fältet Meddelandetyp för arbetsflöde för radartikel.
    * Gruppering – Meddelanden för radartiklar grupperas i ett enda e-postmeddelande.    Enskilt – Ett e-postmeddelande skickas för varje radartikel.  
    * Om du vill att användaren ska ta emot meddelanden i klienten ska du välja kryssrutan Skicka meddelanden i e-post.  
6. Klicka på Spara.
7. Stäng sidan.


