---
title: Ställa in en meddelandeprofil för e-post
description: I denna artikel beskrivs hur du skapar en meddelandeprofil för e-post i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: db6c46d471e3b54982132df3e4819236833cf4a8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292146"
---
# <a name="set-up-an-email-notification-profile"></a>Ställa in en meddelandeprofil för e-post

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du skapar en meddelandeprofil för e-post i Microsoft Dynamics 365 Commerce.

När du skapar kanaler kan du konfigurera en e-postmeddelandeprofil. E-postnotifieringsprofilen definierar händelserna i en försäljningstransaktion (t.ex. skapade order, packade order och fakturerade händelser) som du vill skicka meddelanden till dina kunder för. 

För ytterligare information om e-postkonfiguration, se [konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).



## <a name="create-an-email-template"></a>Skapa en e-postmall

Innan en e-postmeddelandetyp kan aktiveras måste du skapa en e-postmall för organisationen i Commerce headquarters för varje aviseringstyp du vill stödja. I den här mallen definieras ämnes-, avsändar-, standardspråk och e-posttext för alla språk som stöds.

Gör så här om du vill skapa en e-postmall.

1. I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Administrationsinställning \> Parametrar \> Organisationens e-postmallar**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **E-post-ID** ange ett ID för att hjälpa till att identifiera den här mallen.
1. I fältet **Avsändarens namn** anger du avsändarens namn.
1. I **E-postbeskrivning**, ange relevant beskrivning.
1. I fälten **avsändarens e-postadress**, ange avsändarnas e-postadress.
1. I avsnittet **Vanlig**, välj ett standardspråk för e-postmallen. Standardspråket används när det inte finns någon lokalanpassad mall för det angivna språket.
1. Expandera avsnittet **innehåll** i e-postmeddelanden och välj **Ny** om du vill skapa mallinnehåll. För varje innehållsobjekt väljer du språket och tillhandahåller e-postmeddelandets ämnesrad. Om e-postmeddelandet ska ha en brödtext kontrollerar du att kryssrutan **Har brödtext** ärt markerad.
1. Välj **e-postmeddelande** i åtgärdsfönstret för att ange en e-postmall.

I bilden nedan visas några exempel på Inställningar för e-postmallar.

![Inställningar för e-postmall.](media/email-template.png)

Mer information om hur du skapar e-postmallar finns i [Skapa e-postmallar för transaktionshändelser](email-templates-transactions.md). 

## <a name="create-an-email-notification-profile"></a>Skapa en meddelandeprofil för e-post

Skapa en meddelandeprofil för e-post i administration enligt följande instruktioner.

1. I Navigeringsfönstret, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> E-postmeddelandeprofil för Commerce**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Meddelandeprofil för e-post** ange ett namn för att identifiera profilen.
1. Ange relevant beskrivning i fältet **beskrivning**.
1. Ställ in **aktiva** växeln på **ja**.

## <a name="add-a-notification-type"></a>Lägg till en meddelandetyp

Gör så här om du vill skapa en e-posthändelse.

1. I Navigeringsfönstret, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> E-postmeddelandeprofil för Commerce**.
1. Under **Inställningar för butikens e-postmeddelande**, välj **Ny**.
1. Välj rätt **Typ av e-postmeddelande** i listrutan.
1. Välj den e-postmall som du skapat ovan i listrutan **E-post-ID**.
1. Markera kryssrutan **Aktiv**.
1. Klicka på **Spara** i åtgärdsfönstret.

I bilden nedan visas några exempel på Inställningar för meddelande för händelse.

![Inställningar för händelsemeddelande.](media/email-notification-profile.png)


## <a name="schedule-a-recurring-email-notification-process-job"></a>Tidsplana ett återkommande jobb med e-postaviseringar

Om du vill skicka ut e-postmeddelanden måste du köra jobbet **Bearbeta butikorders e-postmeddelande**.

Ställ in ett batchjobb i huvudkontoret för att skicka transaktionsmeddelanden via e-post genom att följa stegen nedan.

1. Gå till **Butik och handel \> Butik och handel IT \> E-post och meddelanden \> Skicka e-postmeddelanden**.
1. I dialogrutan **Bearbeta butikorders e-postmeddelande** välj **Återkommande**.
1. I dialogrutan **Definiera upprepning** välj **Inget slutdatum**.
1. Under **Upprepningsmönster**, välj **Minuter**, och ställ sedan in fältet **Antal** till **1**. Via de här inställningarna kan e-postmeddelandena bearbetas så snabbt som möjligt.
1. Välj **OK** för att återgå till dialogrutan **Bearbeta butikorders e-postmeddelande**.
1. Välj **OK** för att slutföra konfigurationen av jobbet.

## <a name="next-steps"></a>Nästa steg

Innan e-post kan skickas måste du konfigurera den utgående e-posttjänsten. Om du vill ha mer information, se [Konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera och skicka e-post](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Översikt över kanaler](channels-overview.md)

[Förutsättningar för att konfigurera kanaler](channels-prerequisites.md)

[Organisationer och organisationshierarkier – översikt](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
