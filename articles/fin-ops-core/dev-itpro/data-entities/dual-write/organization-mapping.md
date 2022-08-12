---
title: Organisationshierarki i Dataverse
description: I den här artikeln beskrivs integreringen av organisationsinformation mellan appar för ekonomi och drift och Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 2f900637855bee3e21916652a373c683e6bf1392
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112031"
---
# <a name="organization-hierarchy-in-dataverse"></a>Organisationshierarki i Dataverse

[!include [banner](../../includes/banner.md)]



Eftersom Dynamics 365 Finance är ett finansiellt system är *organisation* ett grundläggande begrepp och systeminställningarna börjar med konfigurationen av en organisationshierarki. Affärsekonomi kan sedan spåras på organisationsnivå och även på alla nivåer i organisationshierarkin.

Även om Dataverse inte har begreppet av en organisationshierarki, har den några lösa begrepp, till exempel totala försäljningsintäkter. Som en del av Dataverse-integrationen läggs organisationshierarkins datastruktur till i Dataverse.

## <a name="data-flow"></a>Dataflöde

Ett affärsekosystem som består av appar för ekonomi och drift och Dataverse kommer att fortsätta ha en organisationshierarki. Organisationshierarkin bygger på appar för ekonomi och drift, men den exponeras i Dataverse för information och utbyggbarhet. Följande illustration visar organisationshierarkiinformation som exponeras i Dataverse som ett enkelriktat dataflöde från appar för ekonomi och drift till Dataverse.

![Arkitekturbild.](media/dual-write-data-flow.png)

Organisationshierarkins tabellmappningar är tillgängliga för enkelriktad synkronisering av data från appar för ekonomi och drift till Dataverse.

## <a name="templates"></a>Mallar

En organisation är en grupp personer som arbetar tillsammans för att utföra ett arbete eller uppnå ett mål. Organisationshierarkier representerar relationerna mellan de organisationer som finns i företaget. Du kan definiera följande typer av interna organisationer: juridiska personer, driftenheter och team. Som tabellen nedan visar skapas en samling tabellmappningar för att synkronisera juridiska personer, affärsenheter och relaterad hierarki för organisationshierarki.

Appar för ekonomi och drift | Kundengagemangsappar     | Beskrivning
-----------------------|--------------------------------|---
[Juridiska personer](mapping-reference.md#102) | cdm_companies | 
[Juridiska personer](mapping-reference.md#142) | msdyn_internalorganizations |
[Driftenhet](mapping-reference.md#143) | msdyn_internalorganizations |
[Organisationshierarki – publicerad](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Den här mallen innehåller en enkelriktad synkronisering av tabellen publicerad för organisationshierarki.
[Syften för organisationshierarki](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Den här mallen innehåller en enkelriktad synkronisering av tabellen syfte för organisationshierarki.
[Typ av organisationshierarki](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Den här mallen innehåller en enkelriktad synkronisering av tabellen typ för organisationshierarki.

## <a name="internal-organization"></a>Intern organisation

Intern organisationsinformation i Dataverse kommer från två tabeller **driftenhet** och **juridiska personer**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

