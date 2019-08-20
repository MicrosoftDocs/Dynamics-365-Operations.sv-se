---
title: Organisationshierarki i Common Data Service
description: I det här avsnittet beskrivs integreringen av organisationsinformation mellan Finance and Operations och Common Data Service.
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
ms.openlocfilehash: ca2ac0f9dbb8544b12f23a271423a43b0e601272
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789248"
---
## <a name="organization-hierarchy-in-common-data-service"></a>Organisationshierarki i Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Eftersom Microsoft Dynamics 365 for Finance and Operations är ett finansiellt system är *organisation* ett grundläggande begrepp och systeminställningarna börjar med konfigurationen av en organisationshierarki. Affärsekonomi och åtgärder kan sedan spåras på organisationsnivå och även på alla nivåer i organisationshierarkin.

Även om Common Data Service inte har begreppet av en organisationshierarki, har den några lösa begrepp, till exempel totala försäljningsintäkter. Som en del av Common Data Service-integrationen läggs organisationshierarkins datastruktur till i Common Data Service.

## <a name="data-flow"></a>Dataflöde

Ett affärsekosystem som består av Finance and Operations Common Data Service och kommer att fortsätta att ha en organisationshierarki. Organisationshierarkin bygger på Finance and Operations, men den exponeras i Common Data Service för information och utbyggbarhet. Följande illustration visar organisationshierarkiinformation som exponeras i Common Data Service som ett enkelriktat dataflöde från Finance and Operations till Common Data Service.

![Arkitekturbild](media/dual-write-data-flow.png)

## <a name="templates"></a>Mallar

Organisationshierarkin entitetskartor är tillgängliga för enkelriktad synkronisering av data från Finance and Operations till Common Data Service.

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a>Internt syfte för organisationshierarki

Den här mallen ger enkelriktad synkronisering av organisationshierarkin syftesentitet från Finance and Operations till Dynamics 365 for Customer Engagement.

<!-- ![architecture image](media/dual-write-purpose.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
HIERARCHYTYPE | \> | msdyn\_hierarchypurposetypename
HIERARCHYTYPE | \> | msdyn\_hierarchytype.msdyn\_name
HIERARCHYPURPOSE | \>\> | msdyn\_hierarchypurpose
IMMUTABLE | \>\> | msdyn\_immutable
SETASDEFAULT | \>\> | msdyn\_setasdefault

## <a name="internal-organization-hierarchy-type"></a>Intern typ av organisationshierarki

Den här mallen ger enkelriktad synkronisering av organisationshierarkin typentitet från Finance and Operations till Customer Engagement.

<!-- ![architecture image](media/dual-write-type.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
NAMN | \> | msdyn\_name

## <a name="internal-organization-hierarchy"></a>Intern organisationshierarki

Den här mallen ger enkelriktad synkronisering av organisationshierarkin publicerad entitet från Finance and Operations till Customer Engagement.

<!-- ![architecture image](media/dual-write-organization.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
VALIDTO | \> | msdyn\_validto
VALIDFROM | \> | msdyn\_validfrom
HIERARCHYTYPE | \> | msdyn\_hierarchytypename
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentpartyid
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childpartyid
HIERARCHYTYPE | \> | msdyn\_hierarchytypeid.msdyn\_name
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childid.msdyn\_partynumber
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentid.msdyn\_partynumber

## <a name="internal-organization"></a>Intern organisation

Intern organisationsinformation i Common Data Service kommer från två Finance and Operations-entiteter **driftenhet** och **juridiska personer**.

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a>Driftenhet

Källfält | Mappningstyp | Målfält
---|---|---
LANGUAGEID | \> | msdyn\_languageid
NAMEALIAS | \> | msdyn\_namnalias
NAMN | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
OPERATINGUNITTYPE | \>\> | msdyn\_type

### <a name="legal-entity"></a>Juridisk person

Källfält | Mappningstyp | Målfält
---|---|---
NAMEALIAS | \> | msdyn\_namnalias
LANGUAGEID | \> | msdyn\_languageid
NAMN | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
ingen | \>\> | msdyn\_type
LEGALENTITYID | \> | msdyn\_companycode

## <a name="company"></a>Företag

Ger dubbelriktad synkronisering av information om juridisk person (företag) mellan Finance and Operations och Customer Engagement.

<!-- ![architecture image](media/dual-write-company.png) -->

Källfält | Mappningstyp | Målfält
---|---|---
NAMN | = | cdm\_name
LEGALENTITYID | = | cdm\_companycode
