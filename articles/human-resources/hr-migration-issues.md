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
ms.openlocfilehash: 28c2c10a9293d00e26dfcc80ab08b89a122a6135
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2022
ms.locfileid: "9733482"
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

## <a name="licensing"></a>Licensiering

Licenserna för Dynamics 365 Human Resources ändras inte i följande områden: 

- **Minsta antal för licensinköpskrav**
- **Licenser till en produktionsmiljö och en sandbox-miljö** – Om du har befintliga fristående personallicenser som omfattar en produktionsmiljö och en sandbox-miljö, kommer samma antal licenser att vara tillgängliga i ekonomi- och driftinfrastrukturen.
- **Ytterligare sandbox-licenser** – Om du har köpt ytterligare licens för det fristående personalprogrammet kommer samma antal licenser att vara tillgängliga för sandbox-miljöer i ekonomi- och driftinfrastrukturen. 
