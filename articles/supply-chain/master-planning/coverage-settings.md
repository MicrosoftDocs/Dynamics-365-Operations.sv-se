---
title: Disponeringsinställningar
description: Det här ämnet ger information om de disponeringsinställningar som huvudplaneringen använder för att beräkna artikelbehov.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99e094a7131b6d3a299fc72abd0141529908ddd2
ms.sourcegitcommit: 9e50bee6a67f0fe2fa6f86e02c7e8de16d0e2482
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538904"
---
# <a name="coverage-settings"></a>Disponeringsinställningar

[!include [banner](../includes/banner.md)]

Under huvudplanering används disponeringsinställningar för att beräkna artikelbehov.

Du kan ange disponeringsinställningar på flera sätt:

- Ange disponeringsinställningar för en disponeringsgrupp.

    Du kan skapa en disponeringsgrupp som innehåller inställningar för alla produkter som är länkade till disponeringsgruppen. För att skapa en täckningsgrupp, gå till **huvudplanering &gt; Inställningar &gt; Disponering &gt; Disponeringsgrupper**. Du kan koppla en disponeringsgrupp till en produkt. Om länken är specifik för en plats, ett lagerställe eller en produktdimension, ska du använda fältet **Disponeringsgrupp** på sidan **Artikeldisponering**. Om länken är allmänn, oavsett produktdimensionerna, använder du fältet **Disponeringsgrupp** på snabbfliken **Planera** på sidan **Produktdetaljer** sidan. Som standard, om du inte länkar en täckningsgrupp till en produkt, använder du huvudplaneringen av den allmänna täckningsgruppen som anges på **Huvudplaneringsparametrar**.

- Ange disponeringsinställningar för en produkt.

    Du kan skapa disponeringsinställningar för en specifik produkt. Gå till **Produktinformationshantering &gt; Produkter &gt; Frisläppta produkter**. Välj produkt och gå sedan till Åtgärdsfönster, på fliken **Plan** i grupp **Disponering** och klicka på **Artikeldisponering** för att öppna sidan **Artikeldisponering**. Om produkten redan är länkad till en disponeringsgrupp kan du åsidosätta inställningarna för gruppen med hjälp av fältet **Åsidosätt**. Disponeringinställningarna på sidan**Artikeldisponering** åsidosätter inställningarna på sidan **Disponeringsgrupp**.

- Ange disponeringsinställningar för en produkt med hjälp av en guide.

    Guiden hjälper dig steg för steg genom processen att ställa in de primära parametrarna för artikeldisponering. På åtgärdssidan **Artikeldisponering** klickar du på **Guide** om du vill öppna **Artikeldisponeringsguiden**.

- Ange disponeringsinställningar för en dimensionsgrupp.

    Gå till **Produktinformationshantering &gt; Produkter &gt; Frisläppta produkter**. På sidan **Frisläppt produktdetalj** på snabbfliken **Allmänt** i avsnittet **Administration** klickar du på länken i fältet **Lagringsdimensionsgrupp**. På fältet **Lagringsdimensionsgrupper** markerar du fältet **Disponera per dimension** om du vill skapa disponeringsinställningar för en dimension i lagringsdimensiongruppen. Fält **Disponera per dimension** måste väljas för alla produktdimensioner, t.ex. konfiguration, färg, storlek och stil.

## <a name="additional-resources"></a>Ytterligare resurser

[Huvudplaner](master-plans.md)
