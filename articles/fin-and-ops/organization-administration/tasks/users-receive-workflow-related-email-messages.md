---
title: Låt användare ta emot arbetsflödesrelaterade e-postmeddelanden
description: Du kan konfigurera systemet till att skicka e-postmeddelanden till användare vid arbetsflödesrelaterade händelser.
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6800d02878123388611d35760123d0215e9d539f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "344603"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Låt användare ta emot arbetsflödesrelaterade e-postmeddelanden

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

