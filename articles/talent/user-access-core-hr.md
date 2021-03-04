---
title: Användarna kan komma åt Personal men inte Onboard eller Attract
description: Det här avsnittet beskriver hur du löser problem där en användare kan komma åt Microsoft Dynamics 365 Talent - Personal, men inte Attract eller Onboard.
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
ms.openlocfilehash: 6c384d9a7100982eabd201d910e1bea14355dc1f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462573"
---
# <a name="user-can-access-human-resources-but-not-onboard-or-attract"></a>Användarna kan komma åt Personal men inte Onboard eller Attract

[!include [banner](includes/banner.md)]

**Miljöinformation**

- Microsoft Dynamics Lifecycle Services (LCS)-distributionen gjordes av användare A.
- Användare A lade till användare B som användare av Dynamics 365 Human Resources.

**Utleverans**

Användare B kan komma åt Personal, men inte Talent: Attract eller Talent: appen Onboard. När användaren försöker gå till **Upplevelsappar** tas den till en utvärderingsversion istället.

**Lösning**

Användare B måste tilldelas behörighet för att visa den Microsoft Power Apps-miljö som användaren skapat under etableringsprocessen.

Information finns i avsnittet ”beviljar behörighet för miljön” i [Etablera Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

**Långsiktig lösning**

Microsoft överväger att automatiskt tilldela rätt behörigheter till Onboard och Attract när en användare läggs till Personal.


[!INCLUDE[footer-include](../includes/footer-banner.md)]