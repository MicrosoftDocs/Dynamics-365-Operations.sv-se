---
title: Skapa ett projekt för dataintegrering
description: I detta ämne beskrivs hur du skapar ett projekt för dataintegrering.
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 7841f8b31e0ac1a40dce9acaac747f5f378236e0
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752674"
---
# <a name="create-a-data-integration-project"></a>Skapa ett projekt för dataintegrering

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I detta ämne beskrivs hur du skapar ett projekt för dataintegrering.

1. Logga in på Microsoft Dynamics 365 Finance.
2. Gå till **Arbetsytor \> Datahantering** och välj **Dataentiteter**. Vänta tills alla dataentiteter har uppdaterats innan du går vidare till nästa steg.
3. Öppna [Power Apps-portalen](https://make.powerapps.com/) och gör följande:

    1. Välj lämplig miljö.
    2. I det vänstra navigeringsfönstret väljer du **Dataverse \> Anslutningar**.
    3. Anslut till lämpliga instanser av följande objekt:

        - Dynamics 365
        - Dynamics 365 för Fin & Ops

4. Öppna [Power Apps-miljöerna](https://admin.powerapps.com/environments) och gör följande:

    1. Välj **Dataintegrering**.
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

        - Resultat av kundbetalningsinsikter (CDS till Fin och Ops 10.0.17+)
        - Resultat av kassaflödes tidsserier (CDS till Fin och Ops)
        - Resultat av budgettidsserier (CDS till Fin och Ops)

    2. Ställ in lämplig tidsplanering för varje projekt.

> [!NOTE]
> Om du inte ser de obligatoriska entiteterna i CDS går du till **Kredit och inkasso > Konfigurera > Finance-insikter > Parametrar för ekonomiinsikter**, aktiverar funktionen Prediktioner av kundbetalning och klickar på knappen **Skapa förutsägelsemodell**. När AI-modellens distribution är slutförd (lyckad eller misslyckad), distribueras de CDS-entiteter som behövs för att skapa integreringen i CDS.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
