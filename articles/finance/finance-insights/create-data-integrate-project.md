---
title: Skapa ett projekt för dataintegrering
description: I denna artikel beskrivs hur du skapar ett projekt för dataintegrering.
author: ShivamPandey-msft
ms.date: 05/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 4ff4f88c6c5d55d853aebd7d437bfb107292fb2f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876252"
---
# <a name="create-a-data-integration-project"></a>Skapa ett projekt för dataintegrering

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du skapar ett projekt för dataintegrering.

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

    1. Skapa ett enda dataintegreringsprojekt för var och en av följande mallar med hjälp av den anslutningsuppsättning du just skapat:

        - Resultat av kundbetalningsinsikter (CDS till Fin och Ops 10.0.17+)
        - Resultat av kassaflödes tidsserier (CDS till Fin och Ops)
        - Resultat av budgettidsserier (CDS till Fin och Ops)

      > [!NOTE]
      > Om du skapar flera dataintegrationsprojekt för varje mall kan det leda till fel som spärrar uppdateringarna.

    2. Ställ in lämplig tidsplanering för varje projekt.

> [!NOTE]
> Om du inte ser de obligatoriska entiteterna i Dataverse, gå till **Kredit och inkasso** > **Konfigurera** > **Finance Insights** > **Finance Insights-parametrar**, aktivera funktionen, **Prediktioner av kundbetalning** och välj **Skapa förutsägelsemodell**. När AI-modellens distribution är slutförd måste de Dataverse-entiteter som behövs för att skapa integreringen distribueras.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
