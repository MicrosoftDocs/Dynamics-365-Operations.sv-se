---
title: Ta bort en instans
description: I denna artikel beskrivs hur du tar bort en testkörning eller produktionsmiljö för Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ce676c93e133cc04ad9c49417ed2ca0d6791e93
ms.sourcegitcommit: 1401d66b6b64c590ca1f8f339d622e922920cf15
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/20/2022
ms.locfileid: "9178485"
---
# <a name="remove-an-instance"></a>Ta bort en instans

_**Gäller för:** Personal i den fristående infrastrukturen_ 

> [!NOTE]
> Från och med 2022 juli kan nya Personal-miljöer inte tilldelas för den fristående Personal-infrastrukturen, och nya Microsoft Dynamics Lifecycle Services-projekt (LCS) kan inte skapas i den. Kunder kan distribuera Personalmiljöer på infrastruktur för ekonomi och drift. Mer information finns i [tillhandahålla Personal i infrastruktur för ekonomi och drift](/hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> Infrastrukturen för appar för ekonomi och drift stöder borttagning av en miljö. Mer information om hur du tar bort en miljö finns i [Ta bort en miljö](../fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure.md#delete-an-environment).

I denna artikel förklaras hur du tar bort en testkörning eller produktionsmiljö för Microsoft Dynamics 365 Human Resources.

## <a name="remove-a-test-drive-environment"></a>Ta bort en testkörningsmiljö

Personal testkörning etableras med en 60 dagars giltighetspolicy. Ägare av testkörningsmiljöer kan emellertid välja sina testmiljöer tidigt genom att utföra följande steg. 

1. Gå till [Power Apps administrationscenter](https://admin.businessplatform.microsoft.com/).
2. Välj **Miljö**.
3. Välj testkörningsmiljö som har ett namnmönster ungefär så här: TestDrive – alias@domain
4. Välj **Ta bort** och bekräfta beslutet. 

Den befintliga testkörningsmiljön tas bort. Om det tas bort kan du skaffa en ny testkörningmiljö. 

## <a name="remove-a-production-environment"></a>Ta bort en produktionsmiljö

Den här artikeln förutsätter att du har köpt Personal via en molnbaserad lösningsleverantör (CSP) eller ett arkitekturavtal för företag (EA). 

Eftersom en enda Personal-miljö ingår i en enda Power Apps-miljö finns det två alternativ att ta hänsyn till när du tar bort en miljö. 
- **Ta bort hela Power Apps-miljön.** Detta alternativ är att föredra när Power Apps-miljön uttryckligen skapade i syfte att tillhandahålla Personal, implementeringen precis har börjat eller du har inte några etablerade integreringar.  
- **Endast ta bort Personal.** Detta alternativ är lämpligt om det finns etablerad Power Apps-miljö som är fylld med data som används i Microsoft Power Apps och Power Automate.


> [!Important]
> Innan du tar bort Power Apps-miljön, se till att den inte används för dataintegrering utanför Personals omfattning. Observera även att de standardinställda Power Apps-miljöerna inte kan tas bort. 

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
4. Logga in på LCS med det konto som du använder för din Personal-prenumeration. 
5. Välj Personal-projektet som innehåller miljön. 
6. I LCS-projektet väljer du fliken **-hantering for Personal**. 
7. Välj instansen som du vill ta bort, som bör markeras med distributionsstatusen **Raderad**.
8. Välj **Ta bort instans** och bekräfta ditt val. 

## <a name="recover-a-soft-deleted-environment"></a>Återställa en tyst, borttagen miljö

Om du tar bort den Power Apps-miljö som personalmiljön är ansluten till kommer statusen för personalmiljön i LCS att vara **Temporärt borttagen**. I det här fallet kan användarna inte ansluta till personal.

Så här återställer du miljön:

1. Följ anvisningarna i [Återställ Power Apps-miljön](/power-platform/admin/recover-environment).

2. Kontakta support för att återställa personalmiljön. För mer information, se [Få support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

> [!Warning]
> Power Apps-miljöer sparas bara i sju dagar efter borttagning. Du måste återställa miljön inom sju dagar.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
