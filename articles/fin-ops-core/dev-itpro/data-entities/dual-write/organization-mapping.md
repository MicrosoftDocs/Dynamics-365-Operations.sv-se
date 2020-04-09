---
title: Organisationshierarki i Common Data Service
description: I det här avsnittet beskrivs integreringen av organisationsinformation mellan Finance and Operations-appar och Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: fc5db8d04a2860df0c917816e2910c6fbda941ff
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173164"
---
# <a name="organization-hierarchy-in-common-data-service"></a>Organisationshierarki i Common Data Service

[!include [banner](../../includes/banner.md)]



Eftersom Dynamics 365 Finance är ett finansiellt system är *organisation* ett grundläggande begrepp och systeminställningarna börjar med konfigurationen av en organisationshierarki. Affärsekonomi kan sedan spåras på organisationsnivå och även på alla nivåer i organisationshierarkin.

Även om Common Data Service inte har begreppet av en organisationshierarki, har den några lösa begrepp, till exempel totala försäljningsintäkter. Som en del av Common Data Service-integrationen läggs organisationshierarkins datastruktur till i Common Data Service.

## <a name="data-flow"></a>Dataflöde

Ett affärsekosystem som består av Finance and Operations-appar och Common Data Service kommer att fortsätta att ha en organisationshierarki. Organisationshierarkin bygger på Finance and Operations-appar, men den exponeras i Common Data Service för information och utbyggbarhet. Följande illustration visar organisationshierarkiinformation som exponeras i Common Data Service som ett enkelriktat dataflöde från Finance and Operations-appar till Common Data Service.

![Arkitekturbild](media/dual-write-data-flow.png)

## <a name="templates"></a>Mallar

Organisationshierarkin entitetskartor är tillgängliga för enkelriktad synkronisering av data från Finance and Operations-appar till Common Data Service.

## <a name="templates"></a>Mallar

Produktinformationen innehåller all information som är relaterad till produkten och dess definition, t.ex. produktdimensioner eller spårnings- och lagringsdimensioner. Som framgår av följande tabell skapas en samling med enhetsmappningar för synkronisering av produkter och relaterad information.

Finance and Operations-appar | Andra Dynamics 365-appar | beskrivning
-----------------------|--------------------------------|---
Syften för organisationshierarki | msdyn_internalorganizationhierarchypurposes | Den här mallen innehåller en enkelriktad synkronisering av entiteten syfte för organisationshierarki.
Typ av organisationshierarki | msdyn_internalorganizationhierarchytypes | Den här mallen innehåller en enkelriktad synkronisering av entiteten typ för organisationshierarki.
Organisationshierarki - publicerad | msdyn_internalorganizationhierarchies | Den här mallen innehåller en enkelriktad synkronisering av entiteten publicerad för organisationshierarki.
Driftenhet | msdyn_internalorganizations | 
Juridiska personer | msdyn_internalorganizations | 
Juridiska personer | cdm_companies | Tillhandahåller dubbelriktad synkronisering av information om den juridiska personen (företag).


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a>Intern organisation

Intern organisationsinformation i Common Data Service kommer från två entiteter **driftenhet** och **juridiska personer**.

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]

