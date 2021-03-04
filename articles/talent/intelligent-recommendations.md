---
title: Intelligenta rekommendationer i Attract
description: Det här avsnittet beskriver hur du kan använda maskininlärning för att ge rekommendationer för jobb och jobbsökande i Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 05/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: fa06821c98e42dcd8590a764db9beb4a5c33fca2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462544"
---
# <a name="intelligent-recommendations-in-attract"></a>Intelligenta rekommendationer i Attract

[!include [banner](includes/banner.md)]

Maskininlärning kan hjälpa rekryterare och personalchefer att snabbt identifiera de bästa kandidaterna för en befattning. Den kan också hjälpa potentiella kandidater att hitta en befattning som passar deras profil och intressen. När dessa funktioner används och feedback ges förbättras rekommendationer.

> [!NOTE] 
> - Funktionerna för intelligent rekommendation finns endast med [tillägget för omfattande anställning](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - Funktionen som beskrivs i det här avsnittet är en del av förhandsversionen. Funktionen och dess innehåll kan ändras. Om du vill använda den här funktionen ber du en administratör att aktivera den med hjälp av **administrationscenter** i Attract. Ange **Kandidatrekommendation**, **Jobbrekommendation** och **Rekommendation av potentiell kandidat** till **på**. Mer information finns i [Få åtkomst till förhandsfunktioner i Microsoft Dynamics 365 Talent](./access-preview-feature.md). 


## <a name="candidate-recommendations"></a>Kandidatrekommendationer

Eftersom jobbpubliceringar kan locka hundratals sökande, kan det vara svårt för rekryterare och personalchefer att hitta kandidater vars kvalifikationer och bakgrund bäst matchar befattningen. Genom att analysera sambandet mellan jobbeskrivning och krav och data från kandidatens meritförteckningar och profiler kan maskininlärning användas för att framställa kandidatrekommendationer. Kandidatrekommendationer kan hjälpa rekryterare och personalchefer identifiera de bästa talangerna och flytta dem till intervjufasen snabbare. För alla jobb, om det finns fler än tio kandidater eller potentiella kandidater som har meritförteckningar eller fullständiga profiler kommer de kandidater som bäst uppfyller jobbkraven att visas i avsnittet **Sökande att beakta** på sidan **Jobb**.

För alla rekommenderade kandidater kan du välja **visa kandidat** på kandidatkortet för att granska kandidatens profil och vidta åtgärder för hans eller hennes ansökan. Du kan använda den ellipsformade knappen (**...**) för att öppna kandidatens profil på en ny flik. Du kan också använda den ellipsformade knappen för att ge återkoppling om rekommendationen. På så sätt kan du finjustera rekommendationsmotorn och förbättra framtida rekommendationer. Eventuella rekommendationer som du inte gillar tas bort från avsnittet **sökande att beakta** när du uppdaterar sidan **Jobb**. Du kan använda feedbackkortet för att ange varför du inte tycker att rekommendationen är användbar.

## <a name="job-recommendations"></a>Jobbrekommendationer 

När en potentiell medarbetare använder jobbwebbplatsen för att ansöka om ett jobb, rekommenderar Attract andra lediga befattningar inom organisationen. Dessa rekommendationer baseras på tidigare ansökningar och på potentiella kandidatens profil. Därför hjälper jobbrekommendationer potentiella kandidater att snabbt identifiera vilka jobb som passar dem bäst. Jobbrekommendationer ges till potentiella kandidater om mer än tio jobb publiceras på jobbwebbplatsen. Potentiella kandidater kan öppna detaljerna på en jobbpublicering från rekommendationskortet. De kan också ge feedback om en rekommendationen för att förbättra framtida rekommendationer.

## <a name="prospect-recommendations"></a>Rekommendation av potentiell kandidat 

När en ny befattning blir tillgänglig kan det ta en stund att söka igenom tidigare sökande och hela Talent-nätverket. För att Attract ska hjälpa dig att göra detta kan du använda intelligenta maskininlärningsalgoritmer. Detta innebär att Attract granskar alla kandidater och föreslår de som passar perfekt när du skapar jobbet. För att visa dessa rekommendationer aktiverar du fasen **Potentiella kandidater** för jobbet. Det kan ta upp till en minut för Attract att söka igenom hela kandidatdatabasen för att göra rekommendationer.

Rekommendationerna visas som kort i fliken **Potentiella kandidater** för alla jobb som har fasen **Potentiella kandidater** aktiverad. Dessa kort listar de kompetenser som hittas i den potentiella kandidatens profil samt eventuell utbildningskvalifikationsinformation. Om du hittar en rekommendation som gillar kan du lägga till kandidaten som en potentiell kandidat för jobbet.

> [!NOTE]
> Om du nyligen har börjat använda Attract måste du vänta tills du har minst 10 sökanden som har fullständiga profiler eller meritförteckningar innan du kan använda den här funktionen.

För att undvika eventuell snedvridning i rekommendationerna skannar Attract endast kandidatprofiler för kompetenser, kvalifikationer och andra nyckelord som matchar jobbbeskrivningen. Dessutom tar Attract bort personlig identifieringsinformation från kandidatprofiler före utvärderingen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]