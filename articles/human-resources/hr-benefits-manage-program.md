---
title: Definiera och hantera ett förmånsprogram
description: Personal innehåller en uppsättning av verktyg som kan användas för att ställa in och underhålla förmåner, avdrag och medarbetares kompensationsplaner som en organisation ger eller bearbetar för dess medarbetare. Denna artikel innehåller information om hur du ställer in och hanterar förmåner.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 08b80f4f90ce6b4a286120cd6329a45a4ebd3f71
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877813"
---
# <a name="define-and-manage-a-benefits-program"></a>Definiera och hantera ett förmånsprogram


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Personal innehåller en uppsättning av verktyg som kan användas för att ställa in och underhålla förmåner, avdrag och medarbetares kompensationsplaner som en organisation ger eller bearbetar för dess medarbetare. Denna artikel innehåller information om hur du ställer in och hanterar förmåner.

## <a name="benefit-setup"></a>Förmånsinställning

Innan medarbetare kan anmäla sig till förmåner, måste du skapa elementen för varje förmån. Dessa element kombinerar liknande förmånplaner och definierar standardinställningen, till exempel avdragspriser och redovisningsinformation. Många av de här inställningarna kan justeras när medarbetare anmäler sig till förmånen vid ett senare tillfälle. För varje förmånplan kan en organisation erbjuda flera anmälningsalternativ, eller så kan en medarbetare anmäla sig till planen. 

[![Processflöde för förmåner.](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Förmånselement

Innan du börjar skapa förmåner och anmäla medarbetare till dem, måste du definiera de element som utgör en förmån: typ, plan och alternativ.

-   **Typ** – en samling planer för en viss förmån, till exempel medicin eller parkering.
-   **Plan** – en viss förmån som avtalats från en leverantör.
-   **Alternativ** – omfattningsnivån, exempelvis endast medarbetare eller endast medarbetare och make/maka/partner.

För varje typ av förmån som till exempel syn- eller tandvård kan en organisation erbjuda en eller flera planer till dess medarbetare. För varje plan kan organisationen erbjuda olika alternativ. T.ex. kan medarbetare köpa ytterligare livförsäkringsplaner på ett, två eller tre gånger deras årliga lön. Varje kombination av en plan och alternativ blir en förmån som medarbetare kan anmäla sig till. 

[![förmånsbild.](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>Berättigande
Många faktorer bestämmer berättigande för medarbetaren för olika typer av förmåner som en arbetsgivare erbjuder. När du skapar en förmån i Dynamics 365 Human Resources kan du ange den typ av berättigande som gäller för den förmånen. 

Du kan göra en förmån tillgänglig för alla medarbetare. Vissa företag erbjuder till exempel parkeringstillstånd för alla medarbetare som en löneförmån. När du skapar den här förmånen, förmån du ställer in berättigande till **Alla medarbetare är berättigade**. 

För andra förmåner, exempelvis införsel i lån och skatteavgifter, gäller inte behörigheten. När du skapar dessa typer av förmåner anger du berättigandet som **Kringgå berättigandeprocessen**. 

Slutligen kan förmånsberättigandet vara regelbaserat. Ett företag erbjuder exempelvis två typer av livförsäkringsförmåner för medarbetare. Anställda i ledande befattningar är berättigade till en livförsäkringsplan, medan alla andra heltidsanställda är berättigade till den andra livförsäkringsplanen. I Personal kan du skapa en förmånsberättiganderegel för att hitta alla anställda i ledande befattningar och en annan regel för att hitta alla andra heltidsanställda, och sedan tillämpa dessa regler på lämplig förmån.

## <a name="enrollment"></a>Anmälning
När du har skapat de förmåner som din organisation erbjuder och har fastställt berättigande, kan du registrera dina anställda på förmåner. Du kan skriva in som ett enda anställd i förmåner, eller så kan du anmäla sig många anställd i en eller flera förmåner under en enskild process. 

Ibland stoppar en organisation att erbjuda vissa förmåner. I det här fallet måste du uppdatera förmånen och den personal som registrerats för den. Med massutgångsdatum kan du ändra utgångsdatumet för både en förmån och medarbetarregistreringarna för denna förmån samtidigt. Du kan också markera flera anställd, som är anmäld till en förmån, och ändra slutdatumet för deras disponering. 

På liknande sätt låter dig förlängning av massförmån dig förlänga sista giltighetsdatum för både en förmån och för medarbetarregistreringar för den förmånen om du väljer att erbjuda en förmån längre än vad du ursprungligen planerade.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
