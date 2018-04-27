---
title: "Ta bort en Talent-miljö"
description: "I det här avsnittet får du veta hur du tar bort en testkörning eller produktionsmiljö för Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d1870c84d4d5e7402bae44d192ce7587c2f67fe7
ms.openlocfilehash: 0e7748b079b1cd5c069917d46e05cd281ea6aa01
ms.contentlocale: sv-se
ms.lasthandoff: 04/05/2018

---
# <a name="remove-a-talent-environment"></a>Ta bort en Talent-miljö

I det här avsnittet får du veta hur du tar bort en testkörning eller produktionsmiljö för Microsoft Dynamics 365 for Talent.

## <a name="removing-a-test-drive-environment"></a>Ta bort en testkörningsmiljö

Talent testkörning etableras med en 60 dagars giltighetspolicy. Ägare av testkörningsmiljöer kan emellertid välja sina testmiljöer tidigt genom att utföra följande steg. 

1. Gå till [PowerApps Admin center](https://admin.businessplatform.microsoft.com/).
2. Välj **Miljö**.
3. Välj testkörningsmiljö som har ett namnmönster ungefär så här: TestDrive -alias@domain
4. Välj **Ta bort** och bekräfta beslutet. 

Den befintliga testkörningsmiljön tas bort. Om det tas bort kan du skaffa en ny testkörningmiljö. 

## <a name="removing-a-production-environment"></a>Ta bort en produktionsmiljö

Det här avsnittet förutsätter att du har köpt Talent via en molnbaserad lösningsleverantör (CSP) eller ett arkitekturavtal för företag (EA). 

Eftersom en enda Talent-miljö ”ingår” i en enda PowerApps-miljö, finns det två alternativ att välja mellan. Det första alternativet innebär att ta bort hela PowerApps-miljön. Det andra alternativet innebär att endast Talent tas bort. Det första alternativet är att föredra när du har skapat en PowerApps-miljö uttryckligen i syfte att etablera Talent och du har precis börjat genomförandet eller du har inte några fastställda integrationer. Det andra alternativet är lämpligt om du har en fastställd PowerApps-miljö fylld med rich-data som utnyttjas i PowerApps och flöden.

> [!Important]
> Innan du tar bort PowerApps-miljön, se till att den inte används för integrering av rich-data utanför Talents omfattning. Observera även att de standardinställda PowerApps-miljöerna inte kan tas bort. 

För att ta bort hela PowerApps-miljön, inklusive Talent och tillhörande program och flöden:

1. Gå till [PowerApps Admin center](https://admin.businessplatform.microsoft.com/).
2. Välj **Miljö**.
3. Välj miljön som ska tas bort.
4. Välj **Ta bort** och bekräfta beslutet. 
5. Vänta tills borttagningen har slutförts.
6. Logga in på [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) med det konto som du använder för din Talent-prenumeration. 
7. Välj Talent-projektet som innehåller miljön. 
8. I LCS-projektet väljer du fliken **App-hantering for Talent**. 
9. Markera instansen som du vill ta bort. 
10. Välj **Ta bort instans** och bekräfta ditt val.  

Gör följande om du vill ta bort en Talent-miljö från en befintlig PowerApps-miljö. Observera att behovet av att involvera stöd och kontakta Talent DevOps-teamet är tillfälligt tills funktionen aktiveras direkt i LCS.

1. Kontakta supporten för att initiera en begäran om borttagning.
2. Supportteamet initierar en begäran om borttagning med Talent DevOps-teamet. 
3. Fortsätt efter att du fått veta att miljön har tagits bort.
4.  Logga in på LCS med det konto som du använder för din Talent-prenumeration. 
5. Välj Talent-projektet som innehåller miljön. 
6. I LCS-projektet väljer du fliken **App-hantering for Talent**. 
7. Välj instansen som du vill ta bort, som bör markeras med distributionsstatusen **Misslyckad**.
8. Välj **Ta bort instans** och bekräfta ditt val. 


