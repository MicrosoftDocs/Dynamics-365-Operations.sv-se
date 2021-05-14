---
title: Skapa en försäljningsorder för en konfigurerbar produkt
description: Denna procedur visar hur du tillämpar en konfigureringsmall på en produkt i en försäljningsorder.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8607de5705354aa58c985fb536f3e1d52acd1f37
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921299"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Skapa en försäljningsorder för en konfigurerbar produkt

[!include [banner](../../includes/banner.md)]

Denna procedur visar hur du tillämpar en konfigureringsmall på en produkt i en försäljningsorder. Detta exempel använder högtalarmodellen D0006 i demonstrationsföretaget USMF. Vanligtvis använder en försäljningsorderbehandlare denna procedur.

## <a name="create-a-sales-order"></a>Skapa en försäljningsorder

1. Gå till **Försäljning och marknadsföring \> Arbetsytor \> Försäljningsorderbearbetning och förfrågan**.
1. Välj **Ny**.
1. Välj **Försäljningsorder**.
1. I fältet **kundkonto** välj *US-001*. 
1. Välj **OK**.
1. I fältet **Artikelnummer**, välj *D0006*.
    * För den här uppgiften måste du välja en konfigurerbar produkt.  
1. Välj **Produkt och leverans**.
1. Välj **Konfigurera rad**.
    * Observera att priset har ändrats baserat på den konfiguration som valdes, och att fältet **Inkludera kabel** nu anges som *True*.  
    * Observera valt standardpris och valda inställningar för kabeln.  
1. Välj **Läs in mall**.
    * I det här exemplet visas hur du kan använda en mall för att välja en fördefinierad konfiguration. Om du använder den här proceduren som en uppgiftsguide och vill se andra tillgängliga attributvärden, måste du välja knappen **Lås upp**.  
1. Välj **OK**.
1. Välj **OK**.
1. Visa avsnittet **Raddetaljer**.
1. Välj fliken **Produkt**.
    * Artikelns konfiguration anges nu under produktdimensionerna.  
1. Stäng sidan.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]