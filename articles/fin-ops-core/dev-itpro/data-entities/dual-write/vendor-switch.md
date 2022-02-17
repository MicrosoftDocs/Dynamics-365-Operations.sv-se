---
title: Växla mellan leverantörsdesigner
description: I det här avsnittet beskrivs hur du växlar mellan integreringen av leverantörsdata mellan Ekonomi och Drift-appar och Dataverse.
author: RamaKrishnamoorthy
ms.date: 09/20/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 80de21b5e46e4f274626fa311f16e81312a2f5ab
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062760"
---
# <a name="switch-between-vendor-designs"></a>Växla mellan leverantörsdesigner

[!include [banner](../../includes/banner.md)]





## <a name="vendor-data-flow"></a>Leveranstörsdataflöde 

Om du väljer att använda tabellen **Konto** för att lagra leverantörer av typen **Organisation** och tabellen **Kontakt** för att lagra leverantörer av typen **Person** konfigurerar du följande arbetsflöden. I annat fall är den här konfigurationen inte obligatorisk.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>Använd den utökade leverantörsutformningen för leverantörer av typen organisation

Lösningspaketet **Dynamics365FinanceExtended** innehåller följande mallar för arbetsflödesprocesser. Du ska skapa ett arbetsflöde för varje mall.

+ Skapa leverantörer i tabellen Konton
+ Skapa leverantörer i tabellen Leverantörer
+ Uppdatera leverantörer i tabellen Konton
+ Uppdatera leverantörer i tabellen Leverantörer

Skapa nya arbetsflödesprocesser med hjälp av arbetsflödesprocessmallar genom att följa stegen nedan.

1. Skapa en ny arbetsflödesprocess för tabellen **Leverantör** och välj arbetsflödesprocessmallen **Skapa leverantörer i tabellen Konton**. Välj sedan **OK**. Det här arbetsflödet hanterar scenariot för skapande av leverantörer för tabellen **konto**.

    ![Skapa leverantörer i arbetsflödesprocessen Kontotabell.](media/create_process.png)

2. Skapa en ny arbetsflödesprocess för tabellen **Leverantör** och välj arbetsflödesprocessmallen **Uppdatera leverantörer i tabellen Konton**. Välj sedan **OK**. Det här arbetsflödet hanterar scenariot för uppdatering av leverantörer för tabellen **konto**.
3. Skapa en ny arbetsflödesprocess för tabellen **Konto** och välj arbetsflödesprocessmallen **Skapa leverantörer i tabellen leverantörer**.
4. Skapa en ny arbetsflödesprocess för tabellen **Konto** och välj arbetsflödesprocessmallen **Uppdatera leverantörer i tabellen leverantörer**.
5. Du kan konfigurera arbetsflödena som antingen arbetsflöden i realtid eller i bakgrunden beroende på dina krav. Om du vill konfigurera ett arbetsflöde som ett bakgrundsarbetsflöde väljer du **Konvertera till ett arbetsflöde i bakgrunden**.

    ![Knappen Konvertera till ett arbetsflöde i bakgrunden.](media/background_workflow.png)

6. Aktivera de arbetsflöden som du skapade för tabellerna **Konto** och **Leverantör** för att börja använda tabellen **Konto** för att lagra leverantörsinformation av typen **Organisation**.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>Använd den utökade leverantörsutformningen för leverantörer av typen person

Lösningspaketet **Dynamics365FinanceExtended** innehåller följande mallar för arbetsflödesprocesser. Du ska skapa ett arbetsflöde för varje mall.

+ Skapa leverantörer av typen person i tabellen Leverantörer
+ Skapa leverantörer av typen person i tabellen Kontakter
+ Uppdatera leverantörer av typen person i tabellen Kontakter
+ Uppdatera leverantörer av typen person i tabellen Leverantörer

Skapa nya arbetsflödesprocesser med hjälp av arbetsflödesprocessmallar genom att följa stegen nedan.

1. Skapa en ny arbetsflödesprocess för tabellen **Leverantör** och välj arbetsflödesprocessmallen **Skapa leverantörer av typen person i tabellen Kontakter**. Välj sedan **OK**. Det här arbetsflödet hanterar scenariot för skapande av leverantörer för tabellen **Kontakt**.
2. Skapa en ny arbetsflödesprocess för tabellen **Leverantör** och välj arbetsflödesprocessmallen **Uppdatera leverantörer av typen person i tabellen Kontakter**. Välj sedan **OK**. Det här arbetsflödet hanterar scenariot för uppdatering av leverantörer för tabellen **Kontakt**.
3. Skapa en ny arbetsflödesprocess för tabellen **Kontakt** och välj arbetsflödesprocessmallen **Skapa leverantörer av typen person i tabellen Leverantörer**.
4. Skapa en ny arbetsflödesprocess för tabellen **Kontakt** och välj arbetsflödesprocessmallen **Uppdatera leverantörer av typen person i tabellen Leverantörer**.
5. Du kan konfigurera arbetsflödena som antingen arbetsflöden i realtid eller i bakgrunden beroende på dina krav. Om du vill konfigurera ett arbetsflöde som ett bakgrundsarbetsflöde väljer du **Konvertera till ett arbetsflöde i bakgrunden**.
6. Aktivera de arbetsflöden som du skapade för tabellerna **Kontakt** och **Leverantör** för att börja använda tabellen **Kontakt** för att lagra leverantörsinformation av typen **Person**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]