---
title: Kända problem för Dynamics 365 Human Resources infrastrukturkoppling
description: Den här artikeln innehåller en lista över problem som kan inträffa under Microsoft Dynamics 365 Human Resources infrastrukturkopplingen.
author: twheeloc
ms.date: 10/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5f5981801317ad9647f57a0f68f9b67b592256ab
ms.sourcegitcommit: f96e5dec5a808d9819d2a23b8e15ce00aeff475b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2022
ms.locfileid: "9752701"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-known-issues"></a>Kända problem för Dynamics 365 Human Resources infrastrukturkoppling

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="shared-dataverse-environments"></a>Delade Dataverse-miljöer

Att koppla två appar för ekonomi och drift till samma Dataverse-miljö har inte stöd i ramverket för dubbelriktad skrivning. Om du har en Dataverse-miljö som delas med båda följande objekt, måste du antingen kopiera Dataverse-miljön eller dela den:

- En app för ekonomi och drift
- En aktuell personalmiljö

## <a name="environment-type-requirements"></a>Krav på miljötyp

Följande miljötyper krävs innan du kan migrera:

- Om du inte har några fristående arbetsmiljöer måste du skapa en för att validera migreringen.
- Om du har flera fristående produktionsmiljöer kan en av dem migreras. Kontakta Microsoft Support för att markera de andra miljöerna som sandbox-miljöer.

## <a name="teams-integration"></a>Teams-integration

Det befintliga programmet Personal i Teams skiftas just nu till en Microsoft Power Platform-lösning. Mer information finns [i personalapp i Teams](hr-admin-teams-leave-app.md).

