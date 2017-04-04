---
title: "Definiera och hantera förmåner-program"
description: "Personal innehåller en uppsättning av verktyg som kan användas för att ställa in och underhålla förmåner, avdrag och arbetares kompensationsplaner som en organisation ger eller bearbetar för dess arbetare. Denna artikel innehåller information om hur du ställer in och hanterar förmåner."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 81b5c9056001b26c33b2b42a95711ff5b50243e6
ms.openlocfilehash: 9d00d8f6dfa075f53473af31c257deb57c9efa86
ms.lasthandoff: 03/31/2017


---

# <a name="define-and-manage-a-benefits-program"></a>Definiera och hantera förmåner-program

Personal innehåller en uppsättning av verktyg som kan användas för att ställa in och underhålla förmåner, avdrag och arbetares kompensationsplaner som en organisation ger eller bearbetar för dess arbetare. Det här avsnittet innehåller information om hur du ställer in en Hantera förmåner.

<a name="benefit-setup"></a>Förmånsinställning
-------------

Innan arbetare kan anmäla sig till förmåner, måste du skapa elementen för varje förmån. Dessa element kombinerar liknande förmånplaner och definierar standardinställningen, till exempel avdragspriser och redovisningsinformation. Många av de här inställningarna kan justeras när arbetare anmäler sig till förmånen vid ett senare tillfälle. För varje förmånplan kan en organisation erbjuda flera anmälningsalternativ, eller så kan en arbetare anmäla sig till planen. 

[![Processflöde för förmånen](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Förmånselement
Innan du börjar skapa förmåner och anmäla arbetare till dem, måste du definiera de element som utgör en förmån: typ, plan och alternativ.

-   **Typ** – en samling planer för en viss förmån, till exempel medicin eller parkering.
-   **Plan** – en viss förmån som avtalats från en leverantör.
-   **Alternativ** – omfattningsnivån, exempelvis endast medarbetare eller endast medarbetare och make/maka/partner.

För varje typ av förmån som till exempel syn- eller tandvård kan en organisation erbjuda en eller flera planer till dess arbetare. För varje plan kan organisationen erbjuda olika alternativ. T.ex. kan arbetare köpa ytterligare livförsäkringsplaner på ett, två eller tre gånger deras årliga lön. Varje kombination av en plan och alternativ blir en förmån som arbetare kan anmäla sig till. 

[![pic förmån](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>Berättigande
Många faktorer bestämmer berättigande för arbetaren för olika typer av förmåner som en arbetsgivare erbjuder. Du kan ange vilka kvalifikationer som gäller för denna ersättning när du skapar en förmån i Microsoft Dynamics 365 för operationer. 

Du kan göra en förmån för alla arbetare. Vissa företag ger till exempel parkerings-sekvenser för alla medarbetare som en löneförmåner. När du skapar den här förmånen, förmån du ställer in berättigande till **Alla arbetare är berättigade**. 

För andra fördelar, exempelvis garnishments och skatt importavgifter gäller inte berättigad. Vassle skapa sådana förmåner kan du ange berättigande **kringgå kvalifikationer processen**. 

Dessutom får förmånsberättigande regelbaserad. Ett företag erbjuder två typer av livförsäkringsreserver förmåner till medarbetare. Verkställande anställda som får livförsäkringsreserver planer, medan andra heltidsanställda berättigar till annan försäkring än livförsäkring plan. I Dynamics 365 för operationer kan du skapa en förmånsberättiganderegel vill hitta alla anställda executive och en annan regel för att hitta andra heltidsanställda och sedan tillämpa dessa bestämmelser på lämplig förmånen.

## <a name="enrollment"></a>Anmälning
När du har skapat de förmåner som din organisation erbjuder och har fastställt berättigande, kan du registrera dina anställda på förmåner. Du kan skriva in som ett enda anställd i förmåner, eller så kan du anmäla sig många anställd i en eller flera förmåner under en enskild process. 

Ibland stoppar en organisation att erbjuda vissa förmåner. I det här fallet måste du uppdatera förmånen och personal som deltar i. Massanmälan för förmån upphör att gälla kan du ändra utgångsdatum för både en förmån och arbetare anmälningar för denna ersättning samtidigt. Du kan också markera flera anställd, som är anmäld till en förmån, och ändra slutdatumet för deras disponering. 

På liknande sätt låter dig förlängning av massförmån dig förlänga sista giltighetsdatum för både en förmån och för medarbetarregistreringar för den förmånen om du väljer att erbjuda en förmån längre än vad du ursprungligen planerade.

<a name="see-also"></a>Se även
--------

[Benefit eligibility policies](benefit-eligibility-policies.md)


