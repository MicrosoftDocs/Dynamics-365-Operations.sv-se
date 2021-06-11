---
title: Ange färdigheter
description: Medarbetare och chefer kan ange färdigheter i Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: b24d37292a2e9749fb2fde06b9f03fcd13db0bbe
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076616"
---
# <a name="enter-skills"></a>Ange färdigheter

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan ange eller målfärdigheter verkliga färdigheter för anställd, sökande eller kontakter i Dynamics 365 Human Resources. En målfärdighet är en färdighet som en person planerar att uppnå. En faktisk färdighet är en färdighet som en person redan har.

## <a name="create-a-workflow-to-auto-approve-skills"></a>Skapa ett arbetsflöde för att automatiskt godkänna färdigheter

Om du vill registrera färdigheter utan att kräva godkännande måste du skapa ett arbetsflöde för att godkänna färdigheter automatiskt.

> [!NOTE]
> Kompetenser som anges av arbetare kräver alltid godkännande av chef. Det här arbetsflödet godkänner bara färdigheter som har angetts automatiskt av chefer för deras arbetare.

1. I arbetsytan **Personalhantering** väjer du **Länkar**.

2. Under **Inställningar**, välj **Personalarbetsflöden**.

3. Välj **Ny**.

4. I fönstret **Skapa arbetsflöde**, välj **Kompetens för arbetare**.

   [![Välja arbetsflöde för arbetsfärdigheter](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)

5. I dialogrutan **Öppna denna fil**, välj **Öppna**. Ange din inloggningsuppgifter när du uppmanas.

6. I arbetsflödesredigeraren, välj arbetsflödeselementet **Godkänn färdigheter** och dra det till arbetsflödesredigeraren.

   [![Välj Godkänn arbetsflödeselement för färdigheter](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)

7. Anslut elementet **Start** till elementet **Godkänn färdigheter 1** och anslut till elementet **Godkänn färdigheter 1** till elementet **Avsluta**. Du kanske måste rulla nedåt för att se elementet **Slut**. Du kan dra den närmare de andra elementen.

   [![Anslut arbetsflödeselement](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)

8. Dubbelklicka på arbetsflödeselementet **Godkänn färdigheter 1** och högerklicka sedan på elementet **Steg 1**. Högerklicka på elementet **Steg 1** och välj **Egenskaper**.

9. I fönstret **Egenskaper**, välj **Villkor** i det vänstra navigeringsfönstret.

10. Välj **Kör bara det här steget när följande villkor uppfylls**.

11. Välj **Lägg till villkor**. Efter **Var**, välj **Anställdas självbetjäningsförmåga** och välj sedan **Anställdas självbetjäningsförmåga.Person**. Efter **är**, välj **fält** och välj **Förhållande mellan användare och person.Person**.

    [![Ange villkor](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)

12. Välj **Tilldelning** i det vänstra stapeln.

13. På fliken **Tilldelningstyp**, välj **Hierarki**.

14. På fliken **Hierarkival** i fältet **Hierarkityp:**, välj **Chefshierarki**.

    [![Ange en chefshierarki](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)

15. Välj **Stäng**, välj **Arbetsflöde** i arbetsflödet och välj sedan **Spara och stäng**.

För mer information om att skapa arbetsflöden, se [arbetsflödessystem, översikt](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system?toc=/dynamics365/human-resources/toc.json).

## <a name="enter-skills-for-a-worker"></a>Ange färdigheter för en arbetare

1. Välj en arbetare.

2. I åtgärdsfältet på sidan **Arbetare**, välj **Person** och välj sedan **Färdigheter**.

3. På sidan **Färdigheter** slutför följande fält för varje färdighet:

   - **Färdighet**: välj en färdighet.
   - **Nivåtyp**: Välj **Faktiskt** för en färdighet som a arbetaren redan har eller välj **Mål** för en färdighet som arbetar mot.
   - **Nivå**: Välj en nivå för arbetarens färdighet.
   - **Nivådatum**: Välj ett datum i kalenderverktyget.
   - **Granskare**: vid behov kan du välja en användare från listan. Du kan filtrera sökningen.
   - **Års erfarenhet**: Ange år av erfarenhet.
   - **Verifierat**: Om färdigheten har verifierats ska du markera kryssrutan.
   - **Verifierat av**: Ange namnet på kontrollören.

4. När du har angett färdigheterna väljer du **Spara**.

## <a name="see-also"></a>Se även

[Konfigurera färdigheter](hr-develop-skills.md)<br>
[Mappa kompetenser](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]