---
title: Låt användare ta emot arbetsflödesrelaterade e-postmeddelanden
description: Du kan konfigurera systemet till att skicka e-postmeddelanden till användare vid arbetsflödesrelaterade händelser.
author: jasongre
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 368fe2fbf1f8a1adcabe37ced5ed942f9fb86fc8
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070435"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Låt användare ta emot arbetsflödesrelaterade e-postmeddelanden

[!include [banner](../../includes/banner.md)]


[!INCLUDE [PEAP](../../../../includes/peap-1.md)]

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

> [!NOTE]
> E-postmallarna för arbetsflödet kommer att hämtas från antingen systemets e-postmallar eller organisationens e-postmallar beroende på om arbetsflödet är på systemnivå (inte företagsspecifik) eller arbetsflödet på organisationsnivå (företagsspecifik).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]