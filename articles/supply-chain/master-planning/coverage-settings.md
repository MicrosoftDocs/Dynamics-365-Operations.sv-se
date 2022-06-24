---
title: Disponeringsinställningar
description: Denna artikel ger information om de disponeringsinställningar som huvudplaneringen använder för att beräkna artikelbehov.
author: t-benebo
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
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1218c447a18f79f9a44bfa413a0414d6926d7499
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871961"
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

    Guiden hjälper dig steg för steg genom processen att konfigurera de primära parametrarna för artikeldisponering. På åtgärdssidan **Artikeldisponering** klickar du på **Guide** om du vill öppna **Artikeldisponeringsguiden**.

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