---
title: Använd en relativ sökväg i databindningar för ER-modeller och -format
description: .
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable , ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: a026eec379f98fd32080df50b5e114b423db34ad
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182817"
---
# <a name="use-a-relative-path-in-data-bindings-of-er-models-and-formats"></a>Använd en relativ sökväg i databindningar för ER-modeller och -format

[!include[banner](../includes/banner.md)]

Med verktyget elektronisk rapportering (ER) kan användarna definiera elektroniska formatstrukturer och sedan beskriva hur strukturerna ska fyllas med hjälp av data och algoritmer som finns i programmet. Mer information finns i [Skapa konfigurationer för elektronisk rapportering (ER)](electronic-reporting-configuration.md). Om du vill ange dataflödet för att hämta Finance and Operations-data och använda det för att generera ett elektroniskt dokument måste du göra följande:

- Bind konfigurerade datakällor till element i den utformade domänbaserade datamodellen. Modellstrukturen och de valda datakällorna kan ingå i en komplex hierarkisk struktur. På grund av detta kan slutliga bindningar vara ganska stora och innehålla många element av olika typer (t.ex. relationer, register och metoder). Bindningarna kan bli mindre läsbara och ganska komplicerade att granska och förstå, särskilt inte för andra än ägare. 
- Bind datamodellelement med formatkomponenter för att definiera vilka data som ska hämtas från datamodellen till det genererade formatets utdata.

För att förbättra användbarheten för ER-mappningar har funktionen för relativa sökvägar frigjorts. Som standard är alternativet för relativa sökvägar aktiverat för alla nya instanser av programmet där ER-designupplevelse är aktiverad (Microsoft Dynamics 365 Finance Microsoft Regulatory Configuration Service). Vi har implementerat parametern för relativa sökvägar så att användarna kan fortsätta använda den fullständiga sökvägen när de arbetar med den här presentationen av ER-bindningar.

[![Användarparametrar](./media/relative-path-01.png)](./media/relative-path-01.png)

 
När den relativa sökvägsanvändningsparametern aktiveras, ersätter ett enda @-tecken sökvägen till det överordnade objektet i bindningen för det aktuella modellelementet. Hela bindningssökvägen blir kortare, vilket gör hela mappningen tydligare och lättare att förstå. I de flesta fall behövs ingen ytterligarebläddring i ER-designer för att du ska kunna visa alla bindningar för datamodellen.

[![Modellmappningsdesigner](./media/relative-path-02.png)](./media/relative-path-02.png)
 
När du börjar utforma ett nytt ER-uttryck behöver du bara ange ett tecken för att definiera en bindning till ett fält i den överordnade artikeln.

[![Receptdesigner](./media/relative-path-03.png)](./media/relative-path-03.png)
 
När du bestämmer dig för att ändra datakällan för den överordnade modellposten, med absolut sökvägsanvändning, måste du binda om den här modellartikeln manuellt, liksom alla kapslade objekt, till en ny datakälla. När relativ sökvägsanvändning är aktiverad och du väljer att en ny datakälla ska bindas till ett överordnat objekt, erbjuds du ett alternativ att automatiskt binda om alla kapslade element för det här överordnade objektet med ett klick.

[![Ersätt befintligt sökvägsmeddelande](./media/relative-path-04.png)](./media/relative-path-04.png)
 
Om du bekräftar ombindning av kapslade objekt kommer det nya överordnade objektet att placeras i sökvägen för varje kapslad post som innehåller den befintliga överordnade artikeln.
Den här funktionen avbryter inte kompatibiliteten i ER-ramverket. Alla tidigare utformade ER-konfigurationer fungerar med den här nya funktionen och inga uppgraderingar eller konverteringar krävs.

> [!NOTE]
> Alla ändringar som införs genom massändring av bindningar för kapslade element i modellmappningar sparas korrekt i en konfigurations delta (spårning av ändringar). På så sätt kan kunderna basera sin härledda version av modellmappningarna på en ny basversion av den som har ändrats med hjälp av den nya funktionen.