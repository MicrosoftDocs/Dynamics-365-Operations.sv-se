---
title: Prestanda för tidsplanering av projektresurser
description: Det här avsnittet innehåller information om hur du förbättrar prestanda vid resursplanering för ett stort antal projekt.
author: Yowelle
manager: AnnBe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 10.0.14
ms.search.validFrom: 2020-09-01
ms.openlocfilehash: 988fc83230f08a6534caa7c37784757d73c1cc12
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760669"
---
# <a name="project-resource-scheduling-performance"></a>Prestanda för tidsplanering av projektresurser

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


Prestandafrågor som rör resursplanering kan inträffa när antalet projekt når tusental. För att förbättra resursens schemaläggningsprestanda finns det en funktion som gör att användarna kan förkorta den tid det tar att starta formuläret för resurstillgänglighet. Specifikt tar detta bort synkroniseringsprocessen för resurskapacitetsuppbyggnad och använder tabellen **ResProjectResource** för att påskynda resursökningen. Observera att tabellen **ResRollup** inte längre används.

> [!IMPORTANT]
> Om det finns ett beroende av antingen resurskapacitetssynkroniseringsprocessen eller tabellen **ResProjectResource** inte använder den här funktionen.

## <a name="enable-resource-scheduling-performance-enhancement"></a>Aktivera prestandaförbättring för resursplanering
Gör på följande sätt om du vill aktivera prestandaförbättring för resursplanering.

1. Gå till **funktionenshantera** > **Alla** och i listan funktioner letar du upp **Aktivera funktionen för prestandaförbättring för resursplanering** .
2. Välj **Aktivera nu**.

> [!NOTE]
> Om du inte hittar funktionen i listan väljer du **Sök efter uppdateringar** för att uppdatera listan.

3. Uppdatera din webbläsare och gå till **Projekthantering och redovisning** > **Periodisk** > **Projektresurser** > **Synkronisera resurskalendrarnas kapacitet i alla företag**.
4. Ange **Ta bort befintliga kapacitetsposter** till **Ja** om du vill ta bort tidigare data. Om du vill generera stegvisa data ställer du in den på **Nej** .
5. I fältet **Periodkod** väljer du den period då data ska genereras. Om du väljer en periodkod behöver du inte ange start- och slutdatum.
6. Om du lämnar fältet **periodkod** tomt, ska du välja specifika start- och slutdatum för att generera data.
7. Välj **OK**.

 > [!NOTE]
 > Detta innebär att allmänna data distribueras till tabellen **ResCalendarCapacity** i alla företag i din miljö, så att batch-jobbet bara behöver köras i en juridisk person. Data i det här batchjobbet behövs för att beräkna resurskapacitet genom den associerade kalendern.

8. Gå till **Projekthantering och redovisning** > **Periodisk** > **Projektresurser** > **Fyll i projektresurser i alla företag** och välj sedan **OK**. Det här är datauppgraderingsskriptet för allmänna data i tabellerna **ResProjectResource**, **ResCalendarDateTimeRange** och **ResEffectiveDateTimeRange**. Värden för fältet **PSAPRojSchedRole.RootActivity** uppdateras också. Om det inte körs visas en varning när du försöker köra resursplaneringsåtgärder.
 
## <a name="turn-off-resource-scheduling-performance-enhancement"></a>Inaktivera prestandaförbättring för resursplanering

1. Gå till **funktionenshantera** > **Alla** och sök efter **Aktivera funktionen för prestandaförbättring för resursplanering** .
2. Markera funktionen och välj sedan knappen **Inaktivera**.
3. Uppdatera webbläsaren.
4. Gå till **Projekthantering och redovisning** > **Periodisk** > **Kapacitetssynkronisering** > **Synkronisera kapacitetsuppföljningar för resurs**.
5. På sidan **Resurskapacitetsuppbyggnad** ange **Ta bort befintliga kapacitetsposter** till **Ja** för att ta bort tidigare data. Om du vill generera stegvisa data ställer du in den på **Nej** .
6. I fältet **Periodkod** väljer du den period då data ska genereras. Om du väljer en periodkod behöver du inte ange start- och slutdatum.
7. Om du lämnar fältet **periodkod** tomt, ska du välja specifika start- och slutdatum för att generera data.
8. Välj **OK**.

> [!NOTE]
> Detta innebär att allmänna data distribueras till tabellen **ResRollup** i alla företag i din miljö, så att batch-jobbet bara behöver köras i en juridisk person. Det här batch-jobbet krävs för alla vyer **resurstillgänglighet**. Om det här batchjobbet inte körs **ResRollup** data genereras i farten, vilket kan ta tid.
