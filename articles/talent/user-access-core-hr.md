---
title: Användare kan komma åt Core HR men inte appen Onboard eller Attract
description: Det här avsnittet beskriver hur du löser problem där en användare kan komma åt Dynamics 365 for Talent Core HR, men inte apparna Attract eller Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: ece6a81c54ef1421284fc79ab82ed3e31a972255
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2019
ms.locfileid: "855666"
---
# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a>Användarna kan komma åt Core HR men inte appen Onboard eller Attract

[!include [banner](includes/banner.md)]

**Miljöinformation**

- Microsoft Dynamics Lifecycle Services (LCS)-distributionen gjordes av användare A.
- Användare A lade till användare B som användare av Dynamics 365 for Talent Core HR.

**Utleverans**

Användare B kan komma åt Core HR, men inte Talent: Attract eller Talent: appen Onboard. När användaren försöker gå till **Upplevelsappar** tas den till en utvärderingsversion istället.

**Lösning**

Användare B måste tilldelas behörighet för att visa den Microsoft PowerApps-miljö som användaren skapat under etableringsprocessen.

Information finns i avsnittet ”beviljar behörighet för miljön” i [Etablera Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

**Långsiktig lösning**

Microsoft överväger att automatiskt tilldela rätt behörigheter till Onboard och Attract när en användare läggs till Core HR.
