---
title: Organisationshierarki i Dataverse
description: I det här avsnittet beskrivs integreringen av organisationsinformation mellan Finance and Operations-appar och Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 77625e6e80bfa45add6839df89d9aae27e41d456
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355308"
---
# <a name="organization-hierarchy-in-dataverse"></a>Organisationshierarki i Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Eftersom Dynamics 365 Finance är ett finansiellt system är *organisation* ett grundläggande begrepp och systeminställningarna börjar med konfigurationen av en organisationshierarki. Affärsekonomi kan sedan spåras på organisationsnivå och även på alla nivåer i organisationshierarkin.

Även om Dataverse inte har begreppet av en organisationshierarki, har den några lösa begrepp, till exempel totala försäljningsintäkter. Som en del av Dataverse-integrationen läggs organisationshierarkins datastruktur till i Dataverse.

## <a name="data-flow"></a>Dataflöde

Ett affärsekosystem som består av Finance and Operations-appar och Dataverse kommer att fortsätta att ha en organisationshierarki. Organisationshierarkin bygger på Finance and Operations-appar, men den exponeras i Dataverse för information och utbyggbarhet. Följande illustration visar organisationshierarkiinformation som exponeras i Dataverse som ett enkelriktat dataflöde från Finance and Operations-appar till Dataverse.

![Arkitekturbild.](media/dual-write-data-flow.png)

Organisationshierarkins tabellmappningar är tillgängliga för enkelriktad synkronisering av data från Finance and Operations-appar till Dataverse.

## <a name="templates"></a>Mallar

Produktinformationen innehåller all information som är relaterad till produkten och dess definition, t.ex. produktdimensioner eller spårnings- och lagringsdimensioner. Som framgår av följande tabell skapas en samling med tabellmappningar för synkronisering av produkter och relaterad information.

Finance and Operations-appar | Andra Dynamics 365-appar | beskrivning
-----------------------|--------------------------------|---
Syften för organisationshierarki | msdyn_internalorganizationhierarchypurposes | Den här mallen innehåller en enkelriktad synkronisering av tabellen syfte för organisationshierarki.
Typ av organisationshierarki | msdyn_internalorganizationhierarchytypes | Den här mallen innehåller en enkelriktad synkronisering av tabellen typ för organisationshierarki.
Organisationshierarki - publicerad | msdyn_internalorganizationhierarchies | Den här mallen innehåller en enkelriktad synkronisering av tabellen publicerad för organisationshierarki.
Driftenhet | msdyn_internalorganizations |
Juridiska personer | msdyn_internalorganizations |
Juridiska personer | cdm_companies | Tillhandahåller dubbelriktad synkronisering av information om den juridiska personen (företag).

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a>Intern organisation

Intern organisationsinformation i Dataverse kommer från två tabeller **driftenhet** och **juridiska personer**.

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]