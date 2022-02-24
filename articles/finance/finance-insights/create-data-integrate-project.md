---
title: Skapa ett projekt för dataintegrerare (förhandsversion)
description: I det här ämnet beskrivs hur du skapar ett projekt för dataintegrerare.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: fb17d5e82709a34ff088774d9e9034adb714b58c
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646263"
---
# <a name="create-a-data-integrator-project-preview"></a>Skapa ett projekt för dataintegrerare (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här ämnet beskrivs hur du skapar ett projekt för dataintegrerare.

1. Logga in på Microsoft Dynamics 365 Finance.
2. Gå till **Arbetsytor \> Datahantering** och välj **Dataentiteter**. Vänta tills alla dataentiteter har uppdaterats innan du går vidare till nästa steg.
3. Öppna [Power Apps-portalen](https://make.powerapps.com/) och gör följande:

    1. Välj lämplig miljö.
    2. I det vänstra navigeringsfönstret väljer du **Data \> Anslutningar**.
    3. Anslut till lämpliga instanser av följande objekt:

        - Dynamics 365
        - Dynamics 365 för Fin & Ops

4. Öppna [Power Apps-miljöerna](https://admin.powerapps.com/environments) och gör följande:

    1. Välj **Dataintegrerare**.
    2. Välj **Anslutningsuppsättningar**.
    3. Välj **Ny anslutningsuppsättning**.
    4. Ange ett namn på anslutningen.
    5. Välj lämpliga anslutningar för följande objekt:

        - Dynamics 365
        - Dynamics 365 för Fin & Ops

    6. Välj lämplig organisationsmappning.
    7. Markera **Skapa**.

5. Öppna [Power Apps-miljöerna](https://admin.powerapps.com/environments) och gör följande:  

    1. Skapa dataintegreringsprojekt för följande mallar med hjälp av den anslutningsuppsättning du just skapat:

        - Resultat av kundbetalningsinsikter (CDS till Fin och Ops)
        - Resultat av kassaflödes tidsserier (CDS till Fin och Ops)
        - Resultat av budgettidsserier (CDS till Fin och Ops)

    2. Ställ in lämplig tidsplanering för varje projekt.

> [!NOTE]
> Om du inte ser de obligatoriska entiteterna i CDS går du till **Kredit och inkasso > Konfigurera > Ekonomiinsikter > Parametrar för ekonomiinsikter**, aktiverar funktionen Prediktioner av kundbetalning och klickar på knappen **Skapa förutsägelsemodell**. När AI-modellens distribution är slutförd (lyckad eller misslyckad), distribueras de CDS-entiteter som behövs för att skapa integrationen i CDS.

## <a name="privacy-notice"></a>Sekretesspolicy

Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.
