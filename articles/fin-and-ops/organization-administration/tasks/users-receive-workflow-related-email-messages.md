---
title: Låt användare ta emot arbetsflödesrelaterade e-postmeddelanden
description: Du kan konfigurera systemet till att skicka e-postmeddelanden till användare vid arbetsflödesrelaterade händelser.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
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
ms.openlocfilehash: 5e08f95ef6d263ee0f8c0a94b258c8a2795786bc
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916402"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Låt användare ta emot arbetsflödesrelaterade e-postmeddelanden

[!include [task guide banner](../../includes/task-guide-banner.md)]

Du kan konfigurera systemet till att skicka e-postmeddelanden till användare vid arbetsflödesrelaterade händelser. E-postmeddelanden kan till exempel skickas till användare när dokument tilldelas till dem för godkännande. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

1. Gå till **Navigeringsfönster > Moduler > Systemadministration > Användare > Användare**.
2. Hitta och markera önskad post i listan.
3. Klicka på **Användaralternativ** i **åtgärdsfönstret**.
4. Klicka på fliken **Arbetsflöde**. Kontrollera att avsnittet **Meddelanden** är expanderat. I avsnittet **Meddelanden** kan du ange hur du vill att användaren ska meddelas om arbetsflödesrelaterade händelser.  
5. Välj ett alternativ i fältet **Meddelandetyp för arbetsflöde för radartikel**.
    - Gruppering – Meddelanden för radartiklar grupperas i ett enda e-postmeddelande.
    - Enskilt – Ett e-postmeddelande skickas för varje radartikel.  
    - Om du vill att användaren ska ta emot meddelanden i klienten ska du välja kryssrutan **Skicka meddelanden i e-post**.  
6. Klicka på **Spara**.
7. Stäng sidan.

