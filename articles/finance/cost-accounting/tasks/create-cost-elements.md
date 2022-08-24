---
title: Skapa kostnadselement
description: Det finns flera sätt att skapa kostnadselement inom kostnadsredovisning.
author: kfend
ms.date: 08/29/2018
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
ms.openlocfilehash: 9ca826e54171a3dc3582dc5ceb716ac009d45674
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280733"
---
# <a name="create-cost-elements"></a>Skapa kostnadselement 

[!include [banner](../../includes/banner.md)]

Det finns flera sätt att skapa kostnadselement inom kostnadsredovisning. I den här proceduren visas hur du skapar kostnadselement genom att importera huvudkonton via en datakoppling. Demonstrationsdataföretaget USMF har använts för att skapa denna procedur. Denna procedur är avsedd för en kostnadsredovisningsfunktion som lades till i Dynamics 365 for Operations, version 1611.


## <a name="create-new-cost-elements"></a>Skapa nya kostnadselement
1. Gå till Cost accounting > Dimensions > Cost element dimensions.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Ange eller välj ett värde i fältet Data connector for dimension members.
5. Ange ett värde i fältet Beskrivning.
6. Klicka på Spara.

## <a name="configure-the-data-connector"></a>Konfigurera datakopplingen
1. Klicka på Configure dimension member provider.
2. Ange eller välj ett värde i fältet Chart of accounts.
    * Välj Shared för att använda den delade kontoplanen.  
3. Klicka på Ny.
4. Markera vald rad i listan.
    * Du kan använda filter på konton som uppfyller dina kriterier.  
5. Ange eller välj ett värde i fältet From main account.
6. Ange eller välj ett värde i fältet To main account.
7. Klicka på OK.

## <a name="import-main-accounts"></a>Importera huvudkonton
1. Klicka på Import dimension members.
    * Huvudkonton importeras till kostnadsredovisningen och används som ett kostnadselement.  
2. Klicka på OK.

## <a name="view-the-imported-accounts-as-cost-elements"></a>Visa de importerade kontona som kostnadselement
1. Klicka på View dimension members.
    * Visa de importerade redovisningskontona som kostnadselement i ditt företag som kostnader kan flöda till.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
