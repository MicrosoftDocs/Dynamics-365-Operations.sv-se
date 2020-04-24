---
title: ID-nummer tar emot via mobilappen för lager
description: I det här avsnittet beskrivs hur du ställer in modulen för mobilappen för lager så att du kan använda en mottagningsprocess med ID-nummer som tar emot en process som tar emot fysiskt lager.
author: perlynne
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 98cd608edea1d5365d0d3532244f1fcdb6293d3c
ms.sourcegitcommit: 3a823444005d316bd95fc663e2dbc8252ac7d93a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261378"
---
# <a name="license-plate-receiving-via-the-warehousing-mobile-app"></a>ID-nummer tar emot via mobilappen för lager

I det här avsnittet beskrivs hur du ställer in modulen för mobilappen för lager så att du kan använda en mottagningsprocess med ID-nummer som tar emot en process som tar emot fysiskt lager.

Du kan använda den här funktionen för att snabbt registrera inleveranser av ankommande lager som är relaterat till en leveransavisering (ASN). Systemet skapar automatiskt ett ASN när lagerstyrningsprocesser används för att leverera en överföringsorder. För inköpsorderprocessen kan ett ASN registreras manuellt, eller importeras automatiskt med hjälp av en inkommande ASN-dataenhetsprocess.

ASN-data är kopplade till laster och försändelser via *förpackningsstrukturer*, där lastpallar (överordnade ID-nummerar) kan innehålla lådor (kapslade ID-nummer).

> [!NOTE]
> Om du vill minska antalet lagertransaktioner när förpackningsstrukturer som har kapslade ID-nummer används registrerar systemet den fysiska lagerbehållningen på den överordnade ID-numret. För att den fysiska lagerbehållningen ska kunna initieras från den överordnade ID-numret till de kapslade ID-nummerna, baserat på förpackningsstrukturens data, måste den mobila enheten tillhandahålla ett menyobjekt som baseras på processen för att skapa arbete *paketet för att skapa kapslade ID-nummer*.

<!-- To be used later (will require further editing):
## Warehousing mobile device app processing

When a worker scans an incoming license plate ID, the system initializes a license plate receiving process. Based on this information, the content of the license plate (data coming from the ASN) gets physically registered at the inbound dock location. The flows that follow will depend your business process needs.

## Work policies

As with (for example) the *Report as finished* mobile device menu item process, the license plate receiving process supports several workflows based on the defined setup.

### Work policies with work creation

Registration of physical on-hand where either the same warehouse worker immediately process a put-away work process following the inbound receiving (License plate receiving and put away) or where the registration and put away process gets handled as two different warehouse operations (License plate receiving) following the processing of the put-away work by using the existing work process via another mobile device menu item.

## Work policies without work creation

You can use the license plate receiving process without creating work by using the *License plate receiving without creating work* feature.

By defining **Work policies** with a **Work order type** of *Transfer receipt* and/or *Purchase orders*, and using the **Process** for **License plate receiving (and put away)**, the two Warehousing app process:

- License plate receiving
- License plate receiving and put away

will not create work, but only register the inbound physical inventory on the license plate at the inbound receiving dock.

For more information about the *Report as finished* production scenario, see the [Warehouse work policies overview](warehouse-work-policies.md).

-->

## <a name="show-or-skip-the-receiving-summary-page"></a>Visa eller hoppa över sidan för sammanfattning av inleveranser

Du kan använda funktionen *kontrollera om du vill visa en sida för sammanfattning av inleveranser* för att dra nytta av ett ytterligare detaljerat lagerställeflöde som en del av inleveransprocessen av ID-numret.

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *ange om du ska visa sidan för sammanfattning av inleveranser på mobila enheter*

När den här funktionen är aktiverad visas ett menyalternativ för mobila enheter för inleverans av ID-nummer eller inleverans av ID-nummer och artikelinförsel ger inställningen **sidan för sammanfattning av inleveranser**. Den här inställningen har följande alternativ:

- **Visa en detaljerad sammanfattning** – under inleverans av ID-nummer ser arbetarna en extra sida med den fullständiga ASN-informationen.
- **Hoppa över sammanfattningen** – arbetarna ser inte hela ASN-informationen. Lagerarbetarna inte heller ange en dispositionskod eller lägga till undantag under inleveransprocessen.

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Förhindra överföringsorder – de levererade ID-numren används inte på andra lagerställen än lagerstället vid destinationen

En inleveransprocess av ID-nummer kan inte användas om ett ASN innehåller ett ID-nummer som redan finns och som har fysiska behållningsdata på ett annat lagerställe än det där registrering av ID-numret.

För scenarion för överföringsorder där transportlager inte spårar ID-nummer (och därför inte heller spårar fysisk lagerbehållning per ID-nummer) kan du använda funktionen *Förhindra överföringsorder för de levererade ID-numren att användas på andra lagerställen än lagerstället vid destinationen* för att förhindra att fysiska lageruppdateringar av ID-nummer som är under transport.

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionens namn:** *Förhindra överföringsorder för de levererade ID-numren att användas på andra lagerställen än lagerstället vid destinationen*

Om du vill hantera funktionerna när den här funktionen är tillgänglig följer du stegen nedan.

1. Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.
1. På fliken **allmänt** i snabbfliken **ID-nummer** ställer du in fältet **ID-nummerpolicy för transitlager** till något av följande värden:

    - **Tillåt återanvändning av ej spårat ID-nummer** – systemet fungerar på samma sätt som när funktionen *Förhindra överföringsorder för de levererade ID-numren att användas på andra lagerställen än lagerstället vid destinationen* inte är tillgänglig. Det här värdet är standardinställningen när du först aktiverar funktionen.
    - **Förhindra återanvändning av ej spårat ID-nummer** – endast uppdateringar av lager som är relaterade till ett levererat ID-nummer är tillåtna vid lagerstället på destinationen tills överföringsordern har inlevererats.

## <a name="more-information"></a>Mer information

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

Mer information om menyartiklar för mobila enheter finns i [ställa in mobila enheter för lagerarbete](configure-mobile-devices-warehouse.md).
