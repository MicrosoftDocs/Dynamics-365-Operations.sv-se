---
title: Kundnotifieringar via e-postmeddelande
description: Den här artikeln innehåller information om hur du skapar regler som skickar e-postmeddelanden för fördefinierade händelser.
author: RichdiMSFT
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 469c7fdda40780d6e559819103d73d7a4e7132a1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878290"
---
# <a name="client-alert-notifications-by-email"></a>Kundnotifieringar via e-postmeddelande

[!include [banner](../includes/banner.md)]

Du kan du definiera anpassade notifieringsregler som övervakar filtrerade vyer av data och skicka e-postmeddelanden automatiskt vid fördefinierade händelser. Alternativet att skicka e-postmeddelanden är tillgängligt för alla stödda varningstyper och kan även aktiveras för befintliga varningsregler.

Du kan använda inbyggda kontroller för att skapa notifieringsregler som övervakar filtrerade vyer av batchjobb i systemet. Genom att kontrollera värdet för fältet **Status** kan du konfigurera notifieringsregler som skickar e-post när batch-jobbet misslyckas. När du har skapat dessa notifieringsregler behöver du inte längre kontrollera rapporter för ändringar i affärsdata. I stället kan du låta den intelligenta ändringsidentifieringstjänsten göra övervakningen.

Klientnotifieringar beror på undersystemet för e-post som tillhandahålls via integrering med Microsoft Office. Vi rekommenderar att du använder Simple Mail Transfer Protocol (SMTP)-leverantören, så att e-postdistribution inte är beroende av en lokal e-postklient.

Kunder måste konfigurera integrerade e-posttjänster om du vill skicka meddelanden via e-post. E-postmeddelanden skickas till mottagare på uppdrag av notifieringarnas ägare.

För mer information om hur du konfigurerar e-post, se [konfigurera och skicka e-post](../organization-administration/configure-email.md).

Följande bild visar dialogrutan **Skapa notifieringsregel** som nu innehåller ett alternativ för **skicka e-post**.

[![Dialogrutan Skapa varningsregel, där alternativet Skicka e-post är inställt på Ja.](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)

> [!NOTE]
> När alternativet **skicka e-post** är inställt på **Ja** kommer notifieringar fortsätta levereras från Åtgärdscentret.

## <a name="alert-notification-email-templates"></a>E-postmeddelanden med notifieringar

Tjänsten skickar e-postmeddelanden med hjälp av fördefinierade e-postmallar som ger grundläggande information om varningsmeddelanden.

Följande bild visar strukturen för aviseringar skickas när de tas emot via e-post.

[![Mallbaserade aviseringar för att skapa poster, ändra i fält och ta bort mall.](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]