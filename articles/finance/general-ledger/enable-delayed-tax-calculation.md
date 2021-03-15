---
title: Aktivera fördröjd momsberäkning i journal
description: Det här ämnet förklarar hur du aktiverar funktionen Fördröjd momsberäkning för att förbättra resultat för momsberäkningar när antalet journalrader är mycket stort.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 4ea79747e8e7c078baa6e270ecebf88c4832e079
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968814"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a>Aktivera fördröjd momsberäkning i journal
[!include [banner](../includes/banner.md)]


I det här avsnittet beskrivs hur du kan fördröja momsberäkning för journaler. Den här funktionen ger bättre prestanda vid momsberäkningar när det finns många journalrader.

Som standard beräknas momsbelopp på journalrader när momsrelaterade fält uppdateras. Dessa fält inkluderar fält för momsgrupper och artikelmomsgrupper. Alla uppdateringar av en journalrad gör att momsbeloppen räknas om för alla journalrader. Även om beteendet hjälper användare att se momsbelopp som beräknats i realtid, kan det också påverka prestandan om antalet journalrader är mycket stort.

Med funktionen för fördröjd momsberäkning kan du fördröja momsberäkningen för journaler och därmed lösa prestandaproblem. Om den här funktionen är aktiverad kommer beloppen endast att beräknas när användaren klickar på **Moms** eller bokför journalen.

Du kan fördröja beräkningen av moms på tre nivåer:

- Juridisk person
- Journalnamn
- Journalrubrik

Systemet ger företräde åt inställningen för journalrubriken. Som standard hämtas den här inställningen från journalnamnet. Som standard hämtas inställningen för journalnamn från inställningen på sidan **redovisningsparametrar** när journalnamnet skapas. I följande avsnitt beskrivs hur du aktiverar fördröjd momsberäkning för juridiska personer, journalnamn och journalrubriker.

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a>Aktivera fördröjd momsberäkning på nivån juridisk person

1. Gå till **Redovisning \> Redovisningsinställning \> Allmänna redovisningsparametrar**.
2. På fliken **Moms** på snabbfliken **Allmänt**, ange alternativet **"fördröjd momsberäkning** som **Ja**.

![Bild på allmänna huvudboksparametrar](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a>Aktivera fördröjd momsberäkning på nivån journalnamn

1. Gå till **Redovisning \> Journalkonfiguration \> Journalnamn**.
2. På snabbfliken **Allmänt** i avsnittet **Moms** anger du alternativet **fördröjd momsberäkning** till **Ja**.

![Bild på journalnamn](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a>Aktivera fördröjd momsberäkning på nivån journalrubrik

1. Gå till **Redovisning \> Journalposter \> Allmänna journaler**.
2. Välj **Ny**.
3. Välj ett journalnamn.
4. På fliken **inställningar** ställer du in alternativet **fördröjd momsberäkning** till **ja**.

![Bild på allmän journalsida](media/delayed-tax-calculation-journal-header.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]