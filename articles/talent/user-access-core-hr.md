---
title: Användarna kan komma åt Core HR men inte Onboard eller Attract
description: Det här avsnittet beskriver hur du löser problem där en användare kan komma åt Dynamics 365 Talent - Core HR, men inte Attract eller Onboard.
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
ms.openlocfilehash: 80b1f8aeabfd033f393463f4be5a61447377f2d9
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009316"
---
# <a name="user-can-access-core-hr-but-not-onboard-or-attract"></a>Användarna kan komma åt Core HR men inte Onboard eller Attract

[!include [banner](includes/banner.md)]

**Miljöinformation**

- Microsoft Dynamics Lifecycle Services (LCS)-distributionen gjordes av användare A.
- Användare A lade till användare B som användare av Dynamics 365 Talent: Core HR.

**Utleverans**

Användare B kan komma åt Core HR, men inte Talent: Attract eller Talent: appen Onboard. När användaren försöker gå till **Upplevelsappar** tas den till en utvärderingsversion istället.

**Lösning**

Användare B måste tilldelas behörighet för att visa den Microsoft PowerApps-miljö som användaren skapat under etableringsprocessen.

Information finns i avsnittet ”beviljar behörighet för miljön” i [Etablera Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

**Långsiktig lösning**

Microsoft överväger att automatiskt tilldela rätt behörigheter till Onboard och Attract när en användare läggs till Core HR.
