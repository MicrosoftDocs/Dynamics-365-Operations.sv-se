---
title: Konfigurera mätvärden för IoT-information
description: I det här avsnittet beskrivs hur du ställer in mätvärden för IoT-information.
author: robinarh
ms.date: 04/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f623e49422dfb238415ae450fd0ab354b68c38b
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652091"
---
# <a name="set-up-metrics-for-iot-intelligence"></a>Konfigurera mätvärden för IoT-information

[!include [banner](../../includes/banner.md)]

## <a name="configure-metrics"></a>Konfigurera måtten

Om du vill se tidsseriediagram för dina meddelanden i Microsoft Dynamics 365 Supply Chain Management, måste du ställa in mätvärdena genom att följa dessa steg.

1. Kopiera anslutningssträngen för Redis-cachen:

    1. Gå till Redis-cachen i Azure-portalen.
    2. Gå till **Inställningar** \> **Åtkomstnycklar**.
    3. Kopiera värdet i fältet **Primär anslutningssträng**.

2. I Supply Chain Management navigerar du till **Tillverkningsstyrning \> Inställningar \> IoT-information \> Scenarioparametrar**.
3. På sidan **Scenarioparametrar** på fliken **Tidsserier** i fältet **Anslutningssträng för Redis mätvärden** klistra in anslutningssträngen som du kopierade tidigare. Det här steget gör att måtten från Azure IoT Hub ska visualiseras i Supply Chain Management. När du klistrar in värdet i fältet visas det som **\*\*\*\*\*\***.

    > [!NOTE]
    > När du uppdaterar en av anslutningssträngarna för Redis-cache måste du uppdatera detta fält.

4. Gå till **Produktionskontroll \> Förfrågningar och rapporter \> IoT-information \> Metriska nycklar**.
5. På sidan **Metriska nycklar**, välj **Uppdatera**.
6. I dialogrutan **Uppdatera metriska nycklar**, notera att **Kör i bakgrunden** väljs i fältet. Välj **OK**.

Alla mätnycklar i Redis-cachen hämtas och läggs till i listan över **mätnycklar**. Måttvärden visas inte förrän du [aktiverar scenarierna](iot-scenario-setup.md).

## <a name="configure-the-resource-status-time-series"></a>Konfigurera tidsserien Resursstatus

Konfigurera tidsserierna för **resursstatus** genom att följa dessa steg.

1. I Supply Chain Management, gå till **Produktionskontroll \> Tillverkningskörning \> Resursstatus**.
2. På sidan **Resursstatus** markerar du **Konfigurera**.
2. I dialogrutan **Konfigurera** i listan **Resurs**, välj ett objekt att övervaka.
3. Välj knappen **Redigera** för **Tidsserie 1**.
4. I dialogrutan **Välj tidsserier**, välj ett mätvärde i rutnätet. (Du kan även använda länken **Uppdatera mätnycklar** för att uppdatera metriska nycklar från den här dialogrutan.)
5. Välj **OK** om du vill återgå till dialogrutan **Konfigurera**.
6. Ange ett visningsnamn.
7. I fältet **Visa data från**, välj en tidsram.
8. Välj **OK**.

Diagrammet visas.

## <a name="delete-a-metric-key"></a>Ta bort en måttnyckel

1. I Supply Chain Management, gå till **Produktionskontroll \> Förfrågningar och rapporter \> IoT-information \> Metriska nycklar**.
2. På sidan **Metriska nycklar** väljer du den metriska nyckeln som ska tas bort.
3. Välj **Ta bort**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]