---
title: Fördelar e-postavisering
description: Denna artikel innehåller en översikt över funktionen e-postavisering för förmånshantering i Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/01/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d550cbb2f639535dbb43765c9fb0632a514fbe8c
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229922"
---
# <a name="benefits-email-notification"></a>Fördelar e-postavisering

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [banner](../includes/preview-banner.md)]

Med funktionen e-postnotifiering kan e-postmeddelanden och påminnelser skickas till medarbetarna i följande scenarier:

- Ny anställningsanmälan
- Öppna anmälan
- Kvalificerande livshändelser

Du kan skapa och ställa in flera e-postmallar, och skicka meddelandena med hjälp av arbetsytan för **förmånshantering** och sidan **Anställningsförmåner** . Du kan också spåra historik för meddelanden/påminnelser.

## <a name="set-up-human-resources-shared-parameters"></a>Ställ in delade parametrar för mänskliga resurser

På sidan **Delade personalparametrar** kan du skapa förmånsmallar för olika typer av kommunikation som skickas till anställda eller personalgrupper.

## <a name="create-a-new-email-id-template"></a>Skapa en ny mall för e-post-ID

Gör så här om du vill skapa en ny e-post-ID-mall.

1. Gå till **Systemets e-postmallar**.
2. Välj **Ny**.
3. I fältet **E-post-ID** ange ett namn.
4. Ställ in övriga fält efter behov.
5. Välj **E-postmeddelande** för att ladda upp mallen.
6. På sidan **Delade personalparametrar** välj den nya mallen under **Systemmall** och förflytta under **Mallar för förmåner**.

## <a name="send-email-to-employees"></a>Skicka e-post till medarbetare

För att skicka ett e-postmeddelande till en nyanställd som inte har börjat ännu, följ dessa steg.

1. Öppna arbetsytan **Hantering av förmåner**.
2. Välj panelen för den grupp medarbetare som du vill skicka e-postmeddelandet till.
3. Välj **Skicka e-postmeddelande**.
4. Välj medarbetare som du vill skicka e-postmeddelandet till.
5. Välj **Skicka e-postmeddelande**.
6. Välj mallen som du vill använda.
7. Välj **OK** för att skicka e-post.

    Du kan granska e-postmeddelandet och från medarbetarens på sidan **Arbetarförmån** eller genom att välja **Fördelar med e-posthistorik** i avsnitt **Länkar** på arbetsytan **förmånshantering**. Du kan också skicka e-postmeddelandet från sidan **Arbetsförmånsplan**.

8. För att se fördelarnas e-posthistorik, i arbetsytan **Förmånshantering** i avsnittet **Länkar** väljer **Historik för e-postförmåner**.
9. Visa fullständig e-posthistorik för e-postförmåner som har skickats via e-post. Om du vill granska innehållet i e-postmeddelandet väljer du **Visa meddelande**.
10. Välj **medarbetare**.
11. På sidan **Arbetsförmånsplan** kan du skicka e-post och visa historiken för e-postförmåner.

Arbetsytan för **förmånshantering** innehåller olika arbetsytan. Du kan skicka e-postmeddelanden genom att välja den relaterade mallen. Om den nyanställningsanmälningen har skickats via e-post markerar du **den nyanställning som inte har startats** och väljer sedan länken **Skicka påminnelse**. Du kan välja en påminnelsemall och ange rubriken på meddelandet som första, andra eller tredje påminnelse.
