---
title: Disponeringsinställningar
description: Det här ämnet ger information om de disponeringsinställningar som huvudplaneringen använder för att beräkna artikelbehov.
author: roxanadiaconu
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard, ReqItemTableSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd83e26b7c2792a94d334759790b4f3fbf8c9ff650a188c770359ae6b7f02ff4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758602"
---
# <a name="coverage-settings"></a>Disponeringsinställningar

[!include [banner](../includes/banner.md)]

Under huvudplanering används disponeringsinställningar för att beräkna artikelbehov.

Du kan ange disponeringsinställningar på flera sätt:

- Ange disponeringsinställningar för en disponeringsgrupp.

    Du kan skapa en disponeringsgrupp som innehåller inställningar för alla produkter som är länkade till disponeringsgruppen. För att skapa en täckningsgrupp, gå till **huvudplanering &gt; Inställningar &gt; Disponering &gt; Disponeringsgrupper**. Du kan koppla en disponeringsgrupp till en produkt. Om länken är specifik för en plats, ett lagerställe eller en produktdimension, ska du använda fältet **Disponeringsgrupp** på sidan **Artikeldisponering**. Om länken är allmänn, oavsett produktdimensionerna, använder du fältet **Disponeringsgrupp** på snabbfliken **Planera** på sidan **Produktdetaljer** sidan. Som standard, om du inte länkar en täckningsgrupp till en produkt, använder du huvudplaneringen av den allmänna täckningsgruppen som anges på **Huvudplaneringsparametrar**.

- Ange disponeringsinställningar för en produkt.

    Du kan skapa disponeringsinställningar för en specifik produkt. Gå till **Produktinformationshantering &gt; Produkter &gt; Frisläppta produkter**. Välj produkt och gå sedan till Åtgärdsfönster, på fliken **Plan** i grupp **Disponering** och klicka på **Artikeldisponering** för att öppna sidan **Artikeldisponering**. Om produkten redan är länkad till en disponeringsgrupp kan du åsidosätta inställningarna för gruppen med hjälp av fältet **Åsidosätt**. Disponeringinställningarna på sidan **Artikeldisponering** åsidosätter inställningarna på sidan **Disponeringsgrupp**.

- Ange disponeringsinställningar för en produkt med hjälp av en guide.

    Guiden hjälper dig steg för steg genom processen att ställa in de primära parametrarna för artikeldisponering. På åtgärdssidan **Artikeldisponering** klickar du på **Guide** om du vill öppna **Artikeldisponeringsguiden**.

- Ange disponeringsinställningar för en dimensionsgrupp.

    Gå till **Produktinformationshantering &gt; Produkter &gt; Frisläppta produkter**. På sidan **Frisläppt produktdetalj** på snabbfliken **Allmänt** i avsnittet **Administration** klickar du på länken i fältet **Lagringsdimensionsgrupp**. På fältet **Lagringsdimensionsgrupper** markerar du fältet **Disponera per dimension** om du vill skapa disponeringsinställningar för en dimension i lagringsdimensiongruppen. Fält **Disponera per dimension** måste väljas för alla produktdimensioner, t.ex. konfiguration, färg, storlek och stil.


## <a name="coverage-codes"></a>Täckningskoder

Huvudplanering kan konfigureras till att använda olika återanskaffningsmetoder. Återanskaffningsmetoderna eller partistorleksmetoderna är de tekniker som används i systemet för att fastställa partistorleken för inköpta eller producerade artiklar. 

Varje återanskaffningsmetod tilldelas en av följande täckningskoder:

- **Manuell** - Metoden för partistorlek där systemet inte föreslår inköps-, överförings- eller tillverkningsorder för artikeln. Planeraren för artikeln ansvarar för att skapa de nödvändiga orderna för påfyllnaden av artikeln.
- **Per behov** - Den partistorleksmetod i vilken systemet skapar en planerad inköps-, överförings- eller produktionsorder per behov för artikeln. Detta används vanligtvis för dyra artiklar med återkommande efterfrågan.  
- **Per period** - den partistorleksmetod som kombinerar hela efter frågan för en period till en order för artikeln. Ordern planeras under den första dagen i perioden och dess kvantitet uppfyller nettokraven under den fastställda perioden. Perioden inleds med det första efter frågan av artikeln och täcker den definierade tiden i tid. Nästa period kommer att inledas med nästa behov av artikeln.
- **Minsta/högsta** - den partistorleksmetod som innehåller påfyllningen av lagret upp till en viss nivå när den förutsagda behållningen är under ett tröskelvärde. Kvantiteten för påfyllnaden är differensen mellan den högsta nivån och den förutsagda behållningsnivån.


## <a name="additional-resources"></a>Ytterligare resurser

[Huvudplaner – översikt](master-plans.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]