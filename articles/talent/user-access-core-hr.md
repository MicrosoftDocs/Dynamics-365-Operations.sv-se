---
title: "Användare kan komma åt Core HR men inte appen Onboard eller Attract"
description: "Det här avsnittet beskriver hur du löser problem där en användare kan komma åt Microsoft Dynamics 365 for Talent Core HR men inte apparna Attract eller Onboard."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 2e5d0b1bf993aec89c7d2c6d4916732f5824310d
ms.contentlocale: sv-se
ms.lasthandoff: 12/04/2018

---

# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a>Användare kan komma åt Core HR men inte appen Onboard eller Attract

[!include [banner](includes/banner.md)]

**Miljöinformation**

- Microsoft Dynamics Lifecycle Services (LCS)-distributionen gjordes av användare A.
- Användare A lade till användare B som användare av Microsoft Dynamics 365 for Talent Core HR.

**Utleverans**

Användare B kan komma åt Core HR, men inte Talent: Attract eller Talent: appen Onboard. När användaren försöker gå till **Upplevelsappar** tas den till en utvärderingsversion istället.

**Lösning**

Användare B måste tilldelas behörighet för att visa den Microsoft PowerApps-miljö som användaren skapat under etableringsprocessen.

Information finns i avsnittet ”beviljar behörighet för miljön” i [Etablera Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

**Långsiktig lösning**

Microsoft överväger att automatiskt tilldela rätt behörigheter till Onboard och Attract när en användare läggs till Core HR.

