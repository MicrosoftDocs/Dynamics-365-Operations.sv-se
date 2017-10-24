---
title: "Disponeringsinställningar"
description: "Under huvudplanering används disponeringsinställningar för att beräkna artikelbehov."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fb11a470d98a9742749daaac3244a5bb0d3a689c
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="coverage-settings"></a>Disponeringsinställningar

[!include[banner](../includes/banner.md)]


Under huvudplanering används disponeringsinställningar för att beräkna artikelbehov. 

Du kan ange disponeringsinställningar på flera sätt:

-   Ange disponeringsinställningar för en disponeringsgrupp. Du kan skapa en disponeringsgrupp som innehåller inställningar för alla produkter som är länkade till disponeringsgruppen. Klicka på **Huvudplanering &gt; Inställningar &gt; Disponering &gt; Disponeringsgrupper** för att skapa en disponeringsgrupp. Du kan koppla en disponeringsgrupp till en produkt. Om länken är specifik för en plats, ett lagerställe eller en produktdimension, ska du använda fältet **Disponeringsgrupp** på sidan **Artikeldisponering**. Om länken är allmänn, oavsett produktdimensionerna, använder du **Disponeringsgrupp** på snabbfliken **Planera** på sidan **Produktdetaljer** sidan. Om du inte länkar en disponeringsgrupp till en produkt, använder du den **Huvudplaneringsgrupp** som anges på sidan **Huvudplaneringsparametrar** sidan som standardinställning.

-   Ange disponeringsinställningar för en produkt. Du kan skapa disponeringsinställningar för en specifik produkt. Klicka på **Hantering av produktinformation &gt; Produkter &gt; Frisläppta produkter**. Välj produkt och gå sedan till **Åtgärdsfönster**, på fliken **Planera**, i **Disponeringsgrupp**, och klicka på **Artikeldisponering** för att öppna sidan **Artikeldisponering**. Om produkten redan är länkad till en disponeringsgrupp kan du åsidosätta inställningarna för gruppen med hjälp av fältet **Åsidosätt**. Disponeringinställningarna på sidan**Artikeldisponering** åsidosätter inställningarna på sidan **Disponeringsgrupp**.

<!-- -->

-   Ange disponeringsinställningar för en produkt med hjälp av en guide. Guiden innehåller steg-för-steg-instruktioner för att hjälpa dig ställa in de primära parametrarna för artikeldisponering. På sidan **Artikeldisponering** klickar du på **Guide** om du vill öppna **Artikeldisponeringsguiden**.

<!-- -->

-   Ange disponeringsinställningar för en dimensionsgrupp. Klicka på **Produktinformationshantering &gt; Allmänt &gt; Frisläppta produkter**. På sidan **Frisläppt produktdetalj **, på fliken **Allmänt**, i gruppen **Administration** klickar du på länken **Lagringsdimensionsgrupp**. På fältet **Lagringsdimensionsgrupp** väljer du fältet **Disponera per dimension** om du vill skapa disponeringsinställningar för en dimension i lagringsdimensiongruppen. Alla produktdimensioner, till exempel konfiguration, färg, storlek, och utförande, måste ha fältet **Disponera per dimension** markerat.



<a name="see-also"></a>Se även
--------

[Huvudplaner](master-plans.md)




