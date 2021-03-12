---
title: Rullande inventering av del av platser
description: Planer för rullande inventering guidar de faktiska räkningsoperationerna. Du kan begära att bara specifika produkter och produktvarianter räknas i stället för alla tillgängliga lager på en plats.
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable, WHSRFMenuItemCycleCount, WHSCycleCountPlanListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f228f10c5aeaca3f4fc9b97bf7b6cc4af1592b8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973620"
---
# <a name="partial-location-cycle-counting"></a>Rullande inventering av del av platser

[!include [banner](../includes/banner.md)]

Planer för rullande inventering guidar de faktiska räkningsoperationerna. Du kan begära att bara specifika produkter och produktvarianter räknas i stället för alla tillgängliga lager på en plats.

Du kan vägleda de faktiska räkningsoperationerna genom att använda planer för rullande inventering för att skapa räkningsarbeten. Du kan begära att bara specifika produkter och produktvarianter räknas i stället för alla tillgängliga lager på en plats. Genom att filtrera efter specifika produkter kan lagerchefen minska granskningsomkostnaderna, undvika konsolideringsmisstag och spara tid.

## <a name="how-to-configure-partial-location-cycle-counting"></a>Så här konfigurerar du partiell rullande inventering för plats

När du använder arbetsprocessen för lagerställe för inventeringsoperationer skapas en arbetsrubrik för varje plats. När du definierar planen för rullande inventering kan du använda frågan **Välj platser** för att begränsa arbetet för rullande inventering som skapas. När du väljer produkter för planen för rullande inventering kan du välja både produkt- och produktvariantfrågor för att begränsa det som räknas.

Du kan associera en **arbetsmall** med en plan för rullande inventering för att definiera hur arbetet för rullande inventering ska skapas. Arbetsmallen för inventeringsoperationer refereras direkt från planen för rullande inventering.

När du definierar arbetets mallinformation kan du använda alternativet **Arbetsradbrytningar** för att ange om inventeringsrader för arbete måste grupperas efter artikelnummer eller produktvariantnummer. Denna konfiguration krävs om du vill inventera tillgänglig lagerbehållning endast för specifika produkter på en plats. Arbetsraderna för rullande inventering som skapas får den mängd information som du definierar här, och de vägledda räkneoperationerna hanteras baserat på denna nivå.

Om du associerar planerna för rullande inventering med arbetsmallar genom att använda alternativet **Arbetsradbrytningar**, väljs fältet **Partiell rullande inventering** för det arbete för rullande inventering som skapas, och multipla arbetsrader för rullande inventering skapas baserat på arbetsmallens definition.

Innan arbetet för partiell rullande inventering kan bearbetas, måste du välja minst **Visa artikelnummer** för menyalternativet för mobil enhet som en del av konfigurationen för rullande inventering. Lageroperatören kommer att uppmanas att registrera endast inventeringsinformation som är relaterad till inventeringsraderna (artikelnummer och produktdimensioner). Alla andra tillgängliga lager kommer att ignoreras för den här inventeringsprocessen.

För den partiella rullande inventeringsprocessen kommer datum/tid för **Senaste rullande inventering** inte att uppdateras för platsen även om alla artiklarnas lagerbehållning på en given plats räknas. Den partiella rullande inventeringen tar inte hänsyn till parametern **dagar mellan rullande inventering** på sidan **Planer för rullande inventering** . Partiell rullande inventering stöder inte samtidig räkning av flera artiklar på samma plats. Funktionen för partiell rullande inventering kan leda till att samma lagerställe räknas flera gånger för en artikel när **Bearbetning av plan för rullande inventering** körs. Undvik det scenariot genom att ange filter i fältet **Välj platser**.

> [!NOTE]
> Distributionslagerappen tillhandahåller inte knappen **Lägg till LP eller artikel** när du använder processen för partiell cykelinventering.

## <a name="example"></a>Exempel

I det här exemplet måste bara artikelnumret A0001 räknas i lagerställe 61.

1. En ny arbetsmall skapas för rullande inventering. Alternativet **Arbetsradbrytningar** används för att gruppera inventeringsrader för arbete efter artikelnummer. Det arbete för rullande inventering som skapas kommer får därför rader per artikelnummer. Du kan också gruppera raderna efter produktvariantnummer.
1. En ny plan för rullande inventering som hänvisar till den nyskapade arbetsmallen skapas. Planen för rullande inventering innehåller alla platser på lagerställe 61 (frågan **Välj platser**) som håller lager för artikelnummer A0001. Valet av specifika produkter definieras i avsnittet **Produkturval för rullande inventering**.
1. Du kan välja produkter för planer för rullande inventering genom att ange fältet **tomma platser** till **utelämna tomma**. När planen för rullande inventering bearbetas, skapas delvis rullande inventeringsarbete för artikelnummer A0001. Den faktiska inventeringsprocessen kan utföras genom att använda ett menyalternativ för guidad rullande inventering i en mobil enhet.

## <a name="additional-resources"></a>Ytterligare resurser

[Rullande inventering](cycle-counting.md)
