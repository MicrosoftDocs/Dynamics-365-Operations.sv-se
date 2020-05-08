---
title: Ta bort en instans
description: I det här artikel får du veta hur du tar bort en testkörning eller produktionsmiljö för Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a40b9619e92b81272208ad4241a2455330a342a7
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124438"
---
# <a name="remove-an-instance"></a>Ta bort en instans

I det här artikel får du veta hur du tar bort en testkörning eller produktionsmiljö för Microsoft Dynamics 365 Human Resources.

## <a name="remove-a-test-drive-environment"></a>Ta bort en testkörningsmiljö

Personal testkörning etableras med en 60 dagars giltighetspolicy. Ägare av testkörningsmiljöer kan emellertid välja sina testmiljöer tidigt genom att utföra följande steg. 

1. Gå till [Power Apps administrationscenter](https://admin.businessplatform.microsoft.com/).
2. Välj **Miljö**.
3. Välj testkörningsmiljö som har ett namnmönster ungefär så här: TestDrive - alias@domain
4. Välj **Ta bort** och bekräfta beslutet. 

Den befintliga testkörningsmiljön tas bort. Om det tas bort kan du skaffa en ny testkörningmiljö. 

## <a name="remove-a-production-environment"></a>Ta bort en produktionsmiljö

Den här artikeln förutsätter att du har köpt Personal via en molnbaserad lösningsleverantör (CSP) eller ett arkitekturavtal för företag (EA). 

Eftersom en enda Personal-miljö ”ingår” i en enda Power Apps-miljö, finns det två alternativ att välja mellan. Det första alternativet innebär att ta bort hela Power Apps-miljön. Det andra alternativet innebär att endast Personal tas bort. Det första alternativet är att föredra när du har skapat en Power Apps-miljö uttryckligen i syfte att etablera Personal och du har precis börjat genomförandet eller du har inte några fastställda integrationer. Det andra alternativet är lämpligt om du har en fastställd Power Apps-miljö fylld med rich-data som utnyttjas i Power Apps och Power Automate.

> [!Important]
> Innan du tar bort Power Apps-miljön, se till att den inte används för integrering av rich-data utanför Personal omfattning. Observera även att de standardinställda Power Apps-miljöerna inte kan tas bort. 

För att ta bort hela Power Apps-miljön, inklusive Personal och tillhörande program och flöden:

1. Gå till [Power Apps administrationscenter](https://admin.businessplatform.microsoft.com/).
2. Välj **Miljö**.
3. Välj miljön som ska tas bort.
4. Välj **Ta bort** och bekräfta beslutet. 
5. Vänta tills borttagningen har slutförts.
6. Logga in på [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) med det konto som du använder för din Personal-prenumeration. 
7. Välj Personal-projektet som innehåller miljön. 
8. I LCS-projektet väljer du fliken **-hantering for Personal**. 
9. Markera instansen som du vill ta bort. 
10. Välj **Ta bort instans** och bekräfta ditt val.  

Gör följande om du vill ta bort en Personal-miljö från en befintlig Power Apps-miljö. Observera att behovet av att involvera stöd och kontakta Personal DevOps-teamet är tillfälligt tills funktionen aktiveras direkt i LCS.

1. Kontakta supporten för att initiera en begäran om borttagning.
2. Supportteamet initierar en begäran om borttagning med Personal DevOps-teamet. 
3. Fortsätt efter att du fått veta att miljön har tagits bort.
4.  Logga in på LCS med det konto som du använder för din Personal-prenumeration. 
5. Välj Personal-projektet som innehåller miljön. 
6. I LCS-projektet väljer du fliken **-hantering for Personal**. 
7. Välj instansen som du vill ta bort, som bör markeras med distributionsstatusen **Misslyckad**.
8. Välj **Ta bort instans** och bekräfta ditt val. 