---
title: Arbetare utan anställning
description: Medarbetare utan framtida, aktiva eller historiska anställningar i organisationen visas i formuläret Medarbetare utan anställning.
author: andreabichsel
ms.date: 04/06/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1a137de25924f4c4ec6f6b1fe70f9d21af591c0
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924581"
---
# <a name="workers-without-employment"></a>Arbetare utan anställning

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Medarbetare utan framtida, aktiva eller historiska anställningar i organisationen visas i formuläret **Medarbetare utan anställning**. Arbetare med den här statusen kan visas när du importerar medarbetare utan en anställningspost, eller när du tar bort en medarbetares anställning via **Medarbetare > Anställningshistorik**.

Som standard är formuläret **Medarbetare utan anställning** tillgängligt för följande roller:

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

   [![Lista över filterbehörigheter](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)

3. I kolumnen **Referenser**, välj **Visa menyobjekt**.

4. I kolumnen **Visa menyobjekt** väljer du **HcmWOrkersWithoutEmployment**.

   [![Välj formulär](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)

5. Ange behörigheten **Ta bort** som **Beviljande**.

6. Välj fliken **Opublicerade objekt**.

7. Markera **Publicera alla**.

   [![Publicera ändringar](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]