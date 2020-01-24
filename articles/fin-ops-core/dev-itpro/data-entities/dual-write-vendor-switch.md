---
title: Växla mellan leverantörsdesigner
description: I det här avsnittet beskrivs hur du växlar mellan integreringen av leverantörsdata mellan Finance and Operations-appar och Common Data Service.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 204d788e72e79e7acf744d24cbeacb0f9b47da7d
ms.sourcegitcommit: 3306e451f04df01c51d8d332306b135d8ae1e254
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2019
ms.locfileid: "2902735"
---
# <a name="switch-between-vendor-designs"></a>Växla mellan leverantörsdesigner

[!include [banner](../includes/banner.md)]

## <a name="vendor-data-flow"></a>Leveranstörsdataflöde 

Om du använder Dynamics 365-appar för leverantörshantering och vill isolera leverantörsinformation från kunder kan du använda denna grundläggande leverantörsdesign.  

![Grundläggande leverantörsflöde](media/dual-write-vendor-data-flow.png)
 
Om du vill använda andra Dynamics 365-appar för leverantörshantering och vill fortsätta använda entiteten **Konto** för att lagra leverantörsinformationen kan du använda denna leverantörsdesignen. I den här designen lagras utökad leverantörsinformation, t.ex. spärrstatus för leverantör och leverantörsprofilen lagras i entiteten **leverantörer** i Common Data Service. 

![Utökat leveranstörsflöde](media/dual-write-vendor-detail.jpg)
 
Följ stegen nedan för att använda den utökade leverantörsdesignen: 
 
1. Lösningspaketet **SupplyChainCommon** innehåller arbetsflödesprocessmallar som visas i följande bild.
    > [!div class="mx-imgBorder"]
    > ![Arbetsflödesprocessmallar](media/dual-write-switch-3.png)
2. Skapa nya arbetsflödesprocesser med hjälp av arbetsflödesprocessmallar: 
    1. Skapa en ny arbetsflödesprocess för entiteten **leverantör** med hjälp av arbetsflödesprocessmallen **Skapa leverantörer i entiteten konto** och klicka på **OK**. Det här arbetsflödet hanterar scenariot för skapande av leverantörer för entiteten **konto**.
        > [!div class="mx-imgBorder"]
        > ![Skapa leverantörer i entiteten konto](media/dual-write-switch-4.png)
    2. Skapa en ny arbetsflödesprocess för entiteten **leverantör** med hjälp av arbetsflödesprocessmallen **entiteten uppdatera konto** och klicka på **OK**. Det här arbetsflödet hanterar scenariot för uppdatering av leverantörer för entiteten **konto**. 
        > [!div class="mx-imgBorder"]
        > ![Entiteten uppdatera konto](media/dual-write-switch-5.png)
    3. Skapa nya arbetsflödesprocesser från mallarna som skapas i entiteten **konton**. 
        > [!div class="mx-imgBorder"]
        > ![Skapa leverantörer i entiteten leverantörer](media/dual-write-switch-6.png)
        > [!div class="mx-imgBorder"]
        > ![Uppdatera entiteten leverantörer](media/dual-write-switch-7.png)
    4. Du kan konfigurera arbetsflödena som arbetsflöden i realtid eller i bakgrunden baserat på dina krav. 
        > [!div class="mx-imgBorder"]
        > ![Konvertera till ett arbetsflöde i bakgrunden](media/dual-write-switch-8.png)
    5. Aktivera de arbetsflöden som du skapade på entiteterna **konto** och **leverantör** för att börja använda entiteten **Konto** för lagring av leverantörsinformation. 
 
