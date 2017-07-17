---
title: Rullande inventering av del av platser
description: "Planer för rullande inventering guidar de faktiska räkningsoperationerna. Du kan begära att bara specifika produkter och produktvarianter räknas i stället för alla tillgängliga lager på en plats."
author: perlynne
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
keywords: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 856ac2a61bc06a772b586a0cf77496fc360db623
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# Rullande inventering av del av platser
<a id="partial-location-cycle-counting" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Planer för rullande inventering guidar de faktiska räkningsoperationerna. Du kan begära att bara specifika produkter och produktvarianter räknas i stället för alla tillgängliga lager på en plats.

Du kan vägleda de faktiska räkningsoperationerna genom att använda planer för rullande inventering för att skapa räkningsarbeten. Du kan begära att bara specifika produkter och produktvarianter räknas i stället för alla tillgängliga lager på en plats. Genom att filtrera efter specifika produkter kan lagerchefen minska granskningsomkostnaderna, undvika konsolideringsmisstag och spara tid.

## Så här konfigurerar du partiell rullande inventering för plats
<a id="how-to-configure-partial-location-cycle-counting" class="xliff"></a>
När du använder arbetsprocessen för lagerställe för inventeringsoperationer skapas en arbetsrubrik för varje plats. När du definierar planen för rullande inventering kan du använda frågan **Välj platser** för att begränsa arbetet för rullande inventering som skapas. När du väljer produkter för planen för rullande inventering kan du välja både produkt- och produktvariantfrågor för att begränsa det som räknas. 

Du kan associera en **arbetsmall** med en plan för rullande inventering för att definiera hur arbetet för rullande inventering ska skapas. Arbetsmallen för inventeringsoperationer refereras direkt från planen för rullande inventering. 

När du definierar arbetets mallinformation kan du använda alternativet **Arbetsradbrytningar** för att ange om inventeringsrader för arbete måste grupperas efter artikelnummer eller produktvariantnummer. Denna konfiguration krävs om du vill inventera tillgänglig lagerbehållning endast för specifika produkter på en plats. Arbetsraderna för rullande inventering som skapas får den mängd information som du definierar här, och de vägledda räkneoperationerna hanteras baserat på denna nivå. 

Om du associerar planerna för rullande inventering med arbetsmallar genom att använda alternativet **Arbetsradbrytningar**, väljs fältet **Partiell rullande inventering** för det arbete för rullande inventering som skapas, och multipla arbetsrader för rullande inventering skapas baserat på arbetsmallens definition. 

Innan arbetet för partiell rullande inventering kan bearbetas, måste du välja minst **Visa artikelnummer** för menyalternativet för mobil enhet som en del av konfigurationen för rullande inventering. Lageroperatören kommer att uppmanas att registrera endast inventeringsinformation som är relaterad till inventeringsraderna (artikelnummer och produktdimensioner). Alla andra tillgängliga lager kommer att ignoreras för den här inventeringsprocessen. 

För den partiella rullande inventeringsprocessen kommer datum/tid för **Senaste rullande inventering** inte att uppdateras för platsen.

## Exempel
<a id="example" class="xliff"></a>
I det här exemplet måste bara artikelnumret A0001 räknas i lagerställe 61.

1.  En ny arbetsmall skapas för rullande inventering. Alternativet **Arbetsradbrytningar** används för att gruppera inventeringsrader för arbete efter artikelnummer. Det arbete för rullande inventering som skapas kommer får därför rader per artikelnummer. Du kan också gruppera raderna efter produktvariantnummer.
2.  En ny plan för rullande inventering som hänvisar till den nyskapade arbetsmallen skapas. Planen för rullande inventering innehåller alla platser på lagerställe 61 (frågan **Välj platser**) som håller lager för artikelnummer A0001. Valet av specifika produkter definieras i avsnittet **Produkturval för rullande inventering**.
3.  Du kan välja produkter för planer för rullande inventering genom att ange fältet **Tomma platser** som **Utelämna tomma**. När planen för rullande inventering bearbetas, skapas delvist arbete för rullande inventering för artikelnummer A0001. Den faktiska inventeringsprocessen kan utföras genom att använda ett menyalternativ för guidad rullande inventering i en mobil enhet.



Se även
<a id="see-also" class="xliff"></a>
--------

[Rullande inventering](cycle-counting.md)


