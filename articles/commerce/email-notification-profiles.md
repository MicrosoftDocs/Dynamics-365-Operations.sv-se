---
title: Ange en meddelandeprofil för e-post
description: I det här avsnittet beskrivs hur du skapar en meddelandeprofil för e-post i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9378fb200a239433f2023bb90f72840dace1c0eb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000834"
---
# <a name="set-up-an-email-notification-profile"></a>Ange en meddelandeprofil för e-post


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en meddelandeprofil för e-post i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Innan du skapar kanaler ska du ställa in en profil så att e-postmeddelanden kan skickas ut för olika händelser, t.ex. skapa order, orderleveransstatus och betalningsfel.

För ytterligare information om e-postkonfiguration, se [konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="create-an-email-notification-profile"></a>Skapa en meddelandeprofil för e-post

Skapa en meddelandeprofil för e-post enligt följande instruktioner.

1. I Navigeringsfönstret, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> E-postmeddelandeprofil för Commerce**.
1. Klicka på **Nytt** i Åtgärdsfönstret.
1. I fältet **Meddelandeprofil för e-post** ange ett namn för att identifiera profilen.
1. Ange relevant beskrivning i fältet **beskrivning**.
1. Ställ in **aktiva** växeln på **ja**.

### <a name="create-an-email-template"></a>Skapa en e-postmall

Innan du kan skapa ett e-postmeddelande måste du skapa en organisations e-postmall som innehåller avsändarens e-postinformation och e-postmall.

Gör så här om du vill skapa en e-postmall.

1. I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Administrationsinställning \> Parametrar \> Organisationens e-postmallar**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **E-post-ID** ange ett ID för att hjälpa till att identifiera den här mallen.
1. I fältet **Avsändarens namn** anger du avsändarens namn.
1. I **E-postbeskrivning**, ange relevant beskrivning.
1. I fälten **avsändarens e-postadress**, ange avsändarnas e-postadress.
1. I avsnittet **allmänt** fyller du i valfri information som behövs (t.ex. e-postprioriteten).
1. Expandera avsnittet **innehåll** i e-postmeddelanden och välj **Ny** om du vill skapa mallinnehåll. För varje innehållsobjekt väljer du språket och tillhandahåller e-postmeddelandets ämnesrad. Om e-postmeddelandet ska ha en brödtext kontrollerar du att kryssrutan **Har brödtext** ärt markerad.
1. Välj **e-postmeddelande** i åtgärdsfönstret för att ange en e-postmall.

I bilden nedan visas några exempel på Inställningar för e-postmallar.

![Inställningar för e-postmall](media/email-template.png)

### <a name="create-an-email-event"></a>Skapa en e-posthändelse

Gör så här om du vill skapa en e-posthändelse.

1. I Navigeringsfönstret, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> E-postmeddelandeprofil för Commerce**.
1. Hitta och markera önskad post i listan. 
1. Välj e-postmallen i listrutan **E-post-ID**.
1. Välj rätt **Typ av e-postmeddelande** i listrutan.
1. Markera kryssrutan **Aktiv**.
1. Klicka på **Spara** i åtgärdsfönstret.

I bilden nedan visas några exempel på Inställningar för meddelande för händelse.

![Meddelandeinställningar för händelse](media/email-notification-profile.png)

### <a name="next-steps"></a>Nästa steg

Innan du kan skicka e-post måste du konfigurera den utgående e-posttjänsten och ställa in ett batchjobb. Om du vill ha mer information, se [Konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).


## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Översikt över kanaler](channels-overview.md)

[Förutsättningar för att ställa in kanaler](channels-prerequisites.md)

[Organisationer och organisationshierarkier – översikt](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
