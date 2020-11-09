---
title: Växla mellan leverantörsdesigner
description: I det här avsnittet beskrivs hur du växlar integreringen av leverantörsdata mellan Finance and Operations-appar och Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 0ecc401706911f8b92146b95bb6415185df8b451
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997562"
---
# <a name="switch-between-vendor-designs"></a>Växla mellan leverantörsdesigner

[!include [banner](../../includes/banner.md)]



## <a name="vendor-data-flow"></a>Leveranstörsdataflöde 

Om du väljer att använda entiteten **Konto** för att lagra leverantörer av typen **Organisation** och entiteten **Kontakt** för att lagra leverantörer av typen **Person** konfigurerar du följande arbetsflöden. I annat fall är den här konfigurationen inte obligatorisk.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>Använd den utökade leverantörsutformningen för leverantörer av typen organisation

Lösningspaketet **Dynamics365FinanceExtended** innehåller följande mallar för arbetsflödesprocesser. Du ska skapa ett arbetsflöde för varje mall.

+ Skapa leverantörer i entiteten konton
+ Skapa leverantörer i entiteten leverantörer
+ Uppdatera leverantörer i entiteten konton
+ Uppdatera leverantörer i entiteten leverantörer

Skapa nya arbetsflödesprocesser med hjälp av arbetsflödesprocessmallar genom att följa stegen nedan.

1. Skapa en ny arbetsflödesprocess för entiteten **leverantör** och välj arbetsflödesprocessmallen **Skapa leverantörer i entiteten konton**. Välj sedan **OK**. Det här arbetsflödet hanterar scenariot för skapande av leverantörer för entiteten **konto**.

    ![Arbetsflödesprocess Skapa leverantörer i entiteten konton](media/create_process.png)

2. Skapa en ny arbetsflödesprocess för entiteten **leverantör** och välj arbetsflödesprocessmallen **Uppdatera leverantörer i entiteten konton**. Välj sedan **OK**. Det här arbetsflödet hanterar scenariot för uppdatering av leverantörer för entiteten **konto**.
3. Skapa en ny arbetsflödesprocess för entiteten **Konto** och välj arbetsflödesprocessmallen **Skapa leverantörer i entiteten leverantörer**.
4. Skapa en ny arbetsflödesprocess för entiteten **Konto** och välj arbetsflödesprocessmallen **Uppdatera leverantörer i entiteten leverantörer**.
5. Du kan konfigurera arbetsflödena som antingen arbetsflöden i realtid eller i bakgrunden beroende på dina krav. Om du vill konfigurera ett arbetsflöde som ett bakgrundsarbetsflöde väljer du **Konvertera till ett arbetsflöde i bakgrunden**.

    ![Knappen Konvertera till ett arbetsflöde i bakgrunden](media/background_workflow.png)

6. Aktivera de arbetsflöden som du skapade för entiteterna **konto** och **leverantör** för att börja använda entiteten **Konto** för att lagra leverantörsinformation av typen **Organisation**.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>Använd den utökade leverantörsutformningen för leverantörer av typen person

Lösningspaketet **Dynamics365FinanceExtended** innehåller följande mallar för arbetsflödesprocesser. Du ska skapa ett arbetsflöde för varje mall.

+ Skapa leverantörer av typen person i entiteten leverantörer
+ Skapa leverantörer av typen person i entiteten kontakt
+ Uppdatera leverantörer av typen person i entiteten kontakt
+ Uppdatera leverantörer av typen person i entiteten leverantörer

Skapa nya arbetsflödesprocesser med hjälp av arbetsflödesprocessmallar genom att följa stegen nedan.

1. Skapa en ny arbetsflödesprocess för entiteten **leverantör** och välj arbetsflödesprocessmallen **Skapa leverantörer av typen person i entiteten kontakt**. Välj sedan **OK**. Det här arbetsflödet hanterar scenariot för skapande av leverantörer för entiteten **Kontakt**.
2. Skapa en ny arbetsflödesprocess för entiteten **leverantör** och välj arbetsflödesprocessmallen **Uppdatera leverantörer av typen person i entiteten kontakt**. Välj sedan **OK**. Det här arbetsflödet hanterar scenariot för uppdatering av leverantörer för entiteten **Kontakt**.
3. Skapa en ny arbetsflödesprocess för entiteten **Kontakt** och välj arbetsflödesprocessmallen **Skapa leverantörer av typen person i entiteten leverantörer**.
4. Skapa en ny arbetsflödesprocess för entiteten **Kontakt** och välj arbetsflödesprocessmallen **Uppdatera leverantörer av typen person i entiteten leverantörer**.
5. Du kan konfigurera arbetsflödena som antingen arbetsflöden i realtid eller i bakgrunden beroende på dina krav. Om du vill konfigurera ett arbetsflöde som ett bakgrundsarbetsflöde väljer du **Konvertera till ett arbetsflöde i bakgrunden**.
6. Aktivera de arbetsflöden som du skapade för entiteterna **Kontakt** och **leverantör** för att börja använda entiteten **Kontakt** för att lagra leverantörsinformation av typen **Person**.
