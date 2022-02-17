---
title: Ange en meddelandeprofil för e-post
description: I det här avsnittet beskrivs hur du skapar en meddelandeprofil för e-post i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 02/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 7a7d796a173a6f9dfcd62e1f73e078cac614145e
ms.sourcegitcommit: 2aca3a95d42403c7f5d80dcd5e3ee958dca5c894
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2022
ms.locfileid: "8087877"
---
# <a name="set-up-an-email-notification-profile"></a>Ställa in en meddelandeprofil för e-post

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en meddelandeprofil för e-post i Microsoft Dynamics 365 Commerce.

När du skapar kanaler kan du ställa in en e-postmeddelandeprofil. E-postnotifieringsprofilen definierar händelserna i en försäljningstransaktion (t.ex. skapade order, packade order och fakturerade händelser) som du vill skicka meddelanden till dina kunder för. 

För ytterligare information om e-postkonfiguration, se [konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="create-an-email-notification-profile"></a>Skapa en meddelandeprofil för e-post

Skapa en meddelandeprofil för e-post enligt följande instruktioner.

1. I Navigeringsfönstret, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> E-postmeddelandeprofil för Commerce**.
1. Klicka på **Nytt** i Åtgärdsfönstret.
1. I fältet **Meddelandeprofil för e-post** ange ett namn för att identifiera profilen.
1. Ange relevant beskrivning i fältet **beskrivning**.
1. Ställ in **aktiva** växeln på **ja**.

### <a name="create-an-email-template"></a>Skapa en e-postmall

Innan en e-postmeddelandetyp kan aktiveras måste du skapa en e-postmall för organisationen i Commerce-administration för varje aviseringstyp du vill stödja. I den här mallen definieras ämnes-, avsändar-, standardspråk och e-posttext för alla språk som stöds.

Gör så här om du vill skapa en e-postmall.

1. I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Administrationsinställning \> Parametrar \> Organisationens e-postmallar**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **E-post-ID** ange ett ID för att hjälpa till att identifiera den här mallen.
1. I fältet **Avsändarens namn** anger du avsändarens namn.
1. I **E-postbeskrivning**, ange relevant beskrivning.
1. I fälten **avsändarens e-postadress**, ange avsändarnas e-postadress.
1. I avsnittet **Vanlig**, välj ett standardspråk för e-postmallen. Standardspråket används när det inte finns någon lokaliserad mall för det angivna språket.
1. Expandera avsnittet **innehåll** i e-postmeddelanden och välj **Ny** om du vill skapa mallinnehåll. För varje innehållsobjekt väljer du språket och tillhandahåller e-postmeddelandets ämnesrad. Om e-postmeddelandet ska ha en brödtext kontrollerar du att kryssrutan **Har brödtext** ärt markerad.
1. Välj **e-postmeddelande** i åtgärdsfönstret för att ange en e-postmall.

I bilden nedan visas några exempel på Inställningar för e-postmallar.

![Inställningar för e-postmall.](media/email-template.png)

Mer information om hur du skapar e-postmallar finns i [Skapa e-postmallar för transaktionshändelser](email-templates-transactions.md). 

### <a name="create-an-email-event"></a>Skapa en e-posthändelse

Gör så här om du vill skapa en e-posthändelse.

1. I Navigeringsfönstret, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> E-postmeddelandeprofil för Commerce**.
1. Hitta och markera önskad post i listan. 
1. Välj e-postmallen i listrutan **E-post-ID**.
1. Välj rätt **Typ av e-postmeddelande** i listrutan.
1. Markera kryssrutan **Aktiv**.
1. Klicka på **Spara** i åtgärdsfönstret.

I bilden nedan visas några exempel på Inställningar för meddelande för händelse.

![Inställningar för händelsemeddelande.](media/email-notification-profile.png)

> [!NOTE]
> Den kund som har skapat notifieringstypen kräver att en anpassning måste implementeras innan ett e-postmeddelande kan skickas.

### <a name="next-steps"></a>Nästa steg

Innan du kan skicka e-post måste du konfigurera den utgående e-posttjänsten och ställa in ett batchjobb. Om du vill ha mer information, se [Konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Översikt över kanaler](channels-overview.md)

[Förutsättningar för att ställa in kanaler](channels-prerequisites.md)

[Organisationer och organisationshierarkier – översikt](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
