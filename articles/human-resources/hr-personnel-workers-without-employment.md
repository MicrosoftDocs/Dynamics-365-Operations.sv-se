---
title: Arbetare utan anställning
description: Medarbetare utan framtida, aktiva eller historiska anställningar imom organisationen visas på sidan Medarbetare utan anställning.
author: twheeloc
ms.date: 11/03/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d3b2d5d470e780c708941fd3d08eae1a042b4c03
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689815"
---
# <a name="workers-without-employment"></a>Arbetare utan anställning


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Medarbetare med framtida, aktiva eller historiska anställningar i organisationen visas på sidan **Medarbetare utan anställning**. Arbetare av denna typ kan visas när du importerar medarbetare som inte har någon anställningspost, eller när du tar bort en medarbetares anställning via **Medarbetare \> Anställningshistorik**.

Som standard är sidan **Medarbetare utan anställning** tillgänglig för följande roller:

- Personalassistent
- Personalchef
- Rekryterare
- Kompensations- och förmånsansvarig
- Löneadministratör
- Löneansvarig
- Utbildningsansvarig

I listan **Medarbetare utan anställning** kan du ta bort listade individer. Som standard ges denna behörighet till rollen Personalassistent. Du kan ge den här behörigheten till andra roller med hjälp av följande steg:

1. Välj **Systemadministration** och välj sedan fliken **Säkerhetskonfiguration**.

2. På fliken **behörigheter** filtrera listan **behörigheter** till **Underhåll arbetare**.

   [![Lista över filterbehörigheter.](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)

3. I kolumnen **Referenser**, välj **Visa menyobjekt**.

4. I kolumnen **Visa menyobjekt** väljer du **HcmWOrkersWithoutEmployment**.

   [![Välj formulär.](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)

5. Ange behörigheten **Ta bort** som **Beviljande**.

6. Välj fliken **Opublicerade objekt**.

7. Markera **Publicera alla**.

   [![Publicera ändringar.](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
