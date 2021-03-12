---
title: Skapa en försäljningsorder för en konfigurerbar produkt
description: Denna procedur visar hur du tillämpar en konfigureringsmall på en produkt i en försäljningsorder.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 77404694b3426f9ef051721191b607f91c908cc4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992331"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Skapa en försäljningsorder för en konfigurerbar produkt

[!include [banner](../../includes/banner.md)]

Denna procedur visar hur du tillämpar en konfigureringsmall på en produkt i en försäljningsorder. Detta exempel använder högtalarmodellen D0006 i demonstrationsföretaget USMF. Vanligtvis använder en försäljningsorderbehandlare denna procedur.


## <a name="create-a-sales-order"></a>Skapa en försäljningsorder
1. Klicka på Bearbetning och förfrågan om försäljningsorder.
2. Klicka på Ny.
3. Klicka på Försäljningsorder.
4. Välj US-001 i fältet Customer account. 
5. Klicka på OK.
6. Välj D0006 i fältet Artikelnummer.
    * För den här uppgiften måste du välja en konfigurerbar produkt.  
7. Klicka på Produkt och leverans.
8. Klicka på Konfigurera rad.
    * Observera att priset har ändrats baserat på den konfiguration som valdes, och att fältet Include cable nu anges som true.  
    * Observera valt standardpris och valda inställningar för kabeln.  
9. Klicka på Ladda mall..
    * I det här exemplet visas hur du kan använda en mall för att välja en fördefinierad konfiguration. Om du använder den här proceduren som en uppgiftsguide och vill se andra tillgängliga attributvärden, måste du klicka på knappen Unlock.  
10. Klicka på OK.
11. Klicka på OK.
12. Expandera avsnittet Radinformation.
13. Klicka på fliken Produkt.
    * Artikelns konfiguration anges nu under produktdimensionerna.  
14. Stäng sidan.

## <a name="select-the-product-configuration"></a>Välj produktkonfiguration.

