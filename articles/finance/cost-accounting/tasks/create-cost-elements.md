---
title: Skapa kostnadselement
description: Det finns flera sätt att skapa kostnadselement inom kostnadsredovisning.
author: kfend
ms.date: 08/29/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
ms.openlocfilehash: 0254f486816e852bcda52f90fe4da65c413c7032
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779700"
---
# <a name="create-cost-elements"></a>Skapa kostnadselement 

[!include [banner](../../includes/banner.md)]

Det finns flera sätt att skapa kostnadselement inom kostnadsredovisning. I den här proceduren visas hur du skapar kostnadselement genom att importera huvudkonton via en datakoppling. Demonstrationsdataföretaget USMF har använts för att skapa denna procedur. Denna procedur är avsedd för en kostnadsredovisningsfunktion som lades till i Dynamics 365 for Operations, version 1611.


## <a name="create-new-cost-elements"></a>Skapa nya kostnadselement
1. Gå till **Kostnadsredovisning > Dimensioner > Dimensioner för kostnadselement**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Namn**.
4. Ange eller välj ett värde i fältet **Datakoppling för dimensionsmedlemmar**.
5. I fältet **Beskrivning** anger du ett värde.
6. Klicka på **Spara**.

## <a name="configure-the-data-connector"></a>Konfigurera datakopplingen
1. Klicka på **Konfigurera dimensionsmedlemsprovider**.
2. Ange eller välj ett värde i fältet **kontoplan**.
    * Välj **Delad** för att använda den delade kontoplanen.  
3. Klicka på **Ny**.
4. Markera vald rad i listan.
    * Du kan använda filter på konton som uppfyller dina kriterier.  
5. Ange eller välj ett värde i fältet **Från huvudkonto**.
6. Ange eller välj ett värde i fältet **Till huvudkonto**.
7. Klicka på **OK**.

## <a name="import-main-accounts"></a>Importera huvudkonton
1. Klicka på **Importera dimensionsmedlemmar**.
    * Huvudkonton importeras till kostnadsredovisningen och används som ett kostnadselement.  
2. Klicka på **OK**.

## <a name="view-the-imported-accounts-as-cost-elements"></a>Visa de importerade kontona som kostnadselement
1. Klicka på **Visa dimensionsmedlemmar**.
    * Visa de importerade redovisningskontona som kostnadselement i ditt företag som kostnader kan flöda till.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
