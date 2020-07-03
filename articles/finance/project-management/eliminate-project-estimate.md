---
title: Eliminera en projektuppskattning
description: I det här avsnittet finns information om hur du eliminerar en projektuppskattning när den är slutförd.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
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
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410266"
---
# <a name="eliminate-a-project-estimate"></a>Eliminera en projektuppskattning

[!include [banner](../includes/banner.md)]

Projektuppskattningar ger den ekonomiska vyn för arbete som är uppskattat och planerat för ett projekt. För att arbeta med uppskattningar för ett projekt måste du koppla projektet till ett uppskattningsprojekt. Ett uppskattningsprojekt är alltid baserat på ett befintligt projekt, men flera projekt kan referera till ett enskilt uppskattningsprojekt. Endast projekt med fastpris och investeringsprojekt kan kopplas till uppskattningsprojekt och dessa projekt måste tillhöra samma projektgrupp som uppskattningsprojektet.

Om du vill ta bort ett uppskattningsprojekt måste det vara fullständigt. I följande steg förklaras hur du eliminerar en uppskattning.

1. Gå till **Projekthantering och redovisning** > **Alla projekt** och öppna projektet. 
2. På fliken **Hantera** väljer du **Uppskattningar** och på sidan **Uppskattning** väljer du **eliminera**.
3. På fliken **Eliminera uppskattning** på fliken **Allmänt** anger du följande alternativ:

   - **Periodkod**: Välj periodkoden när du vill välja lämpliga uppskattningsprojekt. 
   - **Uppskattat datum**: Välj lämpligt uppskattat datum för eliminering.
   - **Eliminera med PIA-varningar**: aktivera det här alternativet om du vill att en uppskattning som är associerad med en pågående PIA ska elimineras. Om det här alternativet inte är aktiverat kan eliminering inte fortsätta om det finns icke uppskattade transaktioner. 
   > [!NOTE]
   > Det här alternativet är endast tillgängligt när eliminering används på ett uppskattningsprojekt. Den är inte tillgänglig om du använder periodiska bokföringar. Den här inställningen fungerar med inställningarna på fliken **Uppskatta** på sidan **Projektparametrar** i fältgruppen **Tillåt eliminering när det inte finns uppskattade transaktioner**.
   - **Sätt steget till färdigt**: aktivera det här alternativet om du vill att uppskattningsprojektets fas ska **slutföras** när du har kört elimineringen.
   - **Skriv ut uppskattningslista**: Välj vilken information som ska inkluderas när uppskattningslistan skrivs ut.
   - **Visa informationslogg**: aktivera det här alternativet om du vill visa informationsloggen.
   - **Bokföringsdatum**: Välj bokföringsdatumet för uppskattningen.

4.  Välj **OK**.
5. När elimineringsprocessen har slutförts visas det eliminerade uppskattningsprojektet med ett negativt värde. 

Om du inte har för avsikt att ta bort en uppskattning kan du markera den eliminerade uppskattningen och välja **återför eliminering**.   
