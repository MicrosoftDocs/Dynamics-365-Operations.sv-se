---
title: Klientens notifieringsmeddelanden via e-post
description: Det här avsnittet innehåller information om hur du skapar regler som skickar e-postmeddelanden för fördefinierade händelser.
author: tjvass
manager: AnnBe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 314f04eec04a75aed058c9c38066738e8758f653
ms.sourcegitcommit: 440ebe14ad26574ba227d23ee8370f6b6110645b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2019
ms.locfileid: "373828"
---
# <a name="client-alert-notifications-by-email"></a>Klientens notifieringsmeddelanden via e-post

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

I Microsoft Dynamics 365 for Finance and Operations kan du definiera anpassade notifieringsregler som övervakar filtrerade vyer av data och skicka e-postmeddelanden automatiskt vid fördefinierade händelser. Alternativet att skicka e-postmeddelanden är tillgängligt för alla stödda varningstyper och kan även aktiveras för befintliga varningsregler.

Du kan använda inbyggda kontroller för att skapa notifieringsregler som övervakar filtrerade vyer av batchjobb i systemet. Genom att kontrollera värdet för fältet **Status** kan du konfigurera notifieringsregler som skickar e-post när batch-jobbet misslyckas. När dessa notifieringsregler skapas, behöver du inte längre kontrollera rapporter för ändringar i affärsdata. I stället kan du låta Finance and Operations intelligent ändra identifieringstjänsten göra övervakningen.

Klientnotifieringar beror på undersystemet för e-post som tillhandahålls via integrering med Microsoft Office. Vi rekommenderar att du använder Simple Mail Transfer Protocol (SMTP)-leverantören, så att e-postdistribution inte är beroende av en lokal e-postklient.

Kunder måste konfigurera integrerade e-posttjänster om du vill skicka meddelanden via e-post. E-postmeddelanden skickas till mottagare på uppdrag av notifieringarnas ägare.

För mer information om hur du konfigurerar e-post i Finance and Operation se [konfigurera och skicka e-post](../organization-administration/configure-email.md).

Följande bild visar dialogrutan **Skapa notifieringsregel** som nu innehåller ett alternativ för **skicka e-post**.

[![Dialogrutan Skapa notifieringsregel alternativet Skicka e-post är inställt på Ja](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)

> [!NOTE]
> När alternativet **skicka e-post** är inställt på **Ja** kommer notifieringar fortsätta levereras från Åtgärdscentret.

## <a name="alert-notification-email-templates"></a>E-postmeddelanden med notifieringar

Tjänsten skickar e-postmeddelanden med hjälp av fördefinierade e-postmallar som ger grundläggande information om varningsmeddelanden. Den här informationen innefattar en direkt länk till sidan där notifieringsregeln har definierats.

Följande bild visar strukturen för aviseringar skickas när de tas emot via e-post.

[![Mallbaserade aviseringar för att skapa, ändra och ta bort mallen](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)
