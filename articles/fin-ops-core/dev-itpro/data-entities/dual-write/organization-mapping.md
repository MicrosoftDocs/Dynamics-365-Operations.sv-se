---
title: Organisationshierarki i Dataverse
description: I det här avsnittet beskrivs integreringen av organisationsinformation mellan Finance and Operations-appar och Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: afc1b5996667835c460f467526493380aa2d6403
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062096"
---
# <a name="organization-hierarchy-in-dataverse"></a>Organisationshierarki i Dataverse

[!include [banner](../../includes/banner.md)]



Eftersom Dynamics 365 Finance är ett finansiellt system är *organisation* ett grundläggande begrepp och systeminställningarna börjar med konfigurationen av en organisationshierarki. Affärsekonomi kan sedan spåras på organisationsnivå och även på alla nivåer i organisationshierarkin.

Även om Dataverse inte har begreppet av en organisationshierarki, har den några lösa begrepp, till exempel totala försäljningsintäkter. Som en del av Dataverse-integrationen läggs organisationshierarkins datastruktur till i Dataverse.

## <a name="data-flow"></a>Dataflöde

Ett affärsekosystem som består av Finance and Operations-appar och Dataverse kommer att fortsätta att ha en organisationshierarki. Organisationshierarkin bygger på Finance and Operations-appar, men den exponeras i Dataverse för information och utbyggbarhet. Följande illustration visar organisationshierarkiinformation som exponeras i Dataverse som ett enkelriktat dataflöde från Finance and Operations-appar till Dataverse.

![Arkitekturbild.](media/dual-write-data-flow.png)

Organisationshierarkin tabellkartor är tillgängliga för enkelriktad synkronisering av data från Ekonomi och Drift-appar till Dataverse.

## <a name="templates"></a>Mallar

Produktinformationen innehåller all information som är relaterad till produkten och dess definition, t.ex. produktdimensioner eller spårnings- och lagringsdimensioner. Som framgår av följande tabell skapas en samling med tabellmappningar för synkronisering av produkter och relaterad information.

Finance and Operations-appar | Kundengagemangsappar     | beskrivning
-----------------------|--------------------------------|---
[Juridiska personer](mapping-reference.md#102) | cdm_companies | Tillhandahåller dubbelriktad synkronisering av information om den juridiska personen (företag).
[Juridiska personer](mapping-reference.md#142) | msdyn_internalorganizations |
[Driftenhet](mapping-reference.md#143) | msdyn_internalorganizations |
[Organisationshierarki – publicerad](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Den här mallen innehåller en enkelriktad synkronisering av tabellen publicerad för organisationshierarki.
[Syften för organisationshierarki](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Den här mallen innehåller en enkelriktad synkronisering av tabellen syfte för organisationshierarki.
[Typ av organisationshierarki](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Den här mallen innehåller en enkelriktad synkronisering av tabellen typ för organisationshierarki.

## <a name="internal-organization"></a>Intern organisation

Intern organisationsinformation i Dataverse kommer från två tabeller **driftenhet** och **juridiska personer**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
