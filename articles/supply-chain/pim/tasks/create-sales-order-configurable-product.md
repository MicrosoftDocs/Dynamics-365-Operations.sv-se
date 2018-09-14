--- 
title: "Skapa en försäljningsorder för en konfigurerbar produkt"
description: "Denna procedur visar hur du tillämpar en konfigureringsmall på en produkt i en försäljningsorder."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 646606237f593d24792a0ae072948f2e12782283
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Skapa en försäljningsorder för en konfigurerbar produkt

[!include [task guide banner](../../includes/task-guide-banner.md)]

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


