---
title: "Disponeringsinställningar"
description: "Under huvudplanering används disponeringsinställningar för att beräkna artikelbehov."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c1c5654afa6b592e178af052e3e4a7e246a94c9f
ms.lasthandoff: 03/31/2017


---

# <a name="coverage-settings"></a>Disponeringsinställningar

Under huvudplanering används disponeringsinställningar för att beräkna artikelbehov. 

Du kan ange disponeringsinställningar på flera sätt:

-   Ange disponeringsinställningar för en disponeringsgrupp. Du kan skapa en disponeringsgrupp som innehåller inställningar för alla produkter som är länkade till disponeringsgruppen. Klicka på **huvudplanering &gt;inställningar &gt;täckning &gt;Disponeringsgrupper** om du vill skapa en disponeringsgrupp. Du kan koppla en disponeringsgrupp till en produkt. Om länken är specifik för en plats, ett lagerställe eller en produktdimension, ska du använda fältet **Disponeringsgrupp** på sidan **Artikeldisponering**. Om länken är allmänn, oavsett produktdimensionerna, använder du **Disponeringsgrupp** på snabbfliken **Planera** på sidan **Produktdetaljer** sidan. Om du inte länkar en disponeringsgrupp till en produkt, använder du den **Huvudplaneringsgrupp** som anges på sidan **Huvudplaneringsparametrar** sidan som standardinställning.

-   Ange disponeringsinställningar för en produkt. Du kan skapa disponeringsinställningar för en specifik produkt. Klicka på **produktinformationshantering &gt;produkter &gt;frisläppta produkter**. Markerar du produkten i den **åtgärdsfönstret**klickar du på den **planera** fliken den **disponeringsgrupp**, klickar du på **artikeldisponering** så att den **artikeldisponering** sida. Om produkten redan är länkad till en disponeringsgrupp kan du åsidosätta inställningarna för gruppen med hjälp av fältet **Åsidosätt**. Disponeringinställningarna på sidan** Artikeldisponering** åsidosätter inställningarna på sidan **Disponeringsgrupp**.

<!-- -->

-   Ange disponeringsinställningar för en produkt med hjälp av en guide. Guiden innehåller steg-för-steg-instruktioner för att hjälpa dig ställa in de primära parametrarna för artikeldisponering. På sidan **Artikeldisponering** klickar du på **Guide** om du vill öppna **Artikeldisponeringsguiden**.

<!-- -->

-   Ange disponeringsinställningar för en dimensionsgrupp. Klicka på **produktinformationshantering &gt;gemensamma &gt;frisläppta produkter**. På den ** ut produktinformation ** på sidan i **allmänna** fliken den **Administration** grupp genom att klicka på den **lagringsdimensionsgrupp** länk. På fältet **Lagringsdimensionsgrupp** väljer du fältet **Disponera per dimension** om du vill skapa disponeringsinställningar för en dimension i lagringsdimensiongruppen. Alla produktdimensioner, till exempel konfiguration, färg, storlek, stil, behöver den **Disponera per dimension** markerat.



<a name="see-also"></a>Se även
--------

[Master plans](master-plans.md)


