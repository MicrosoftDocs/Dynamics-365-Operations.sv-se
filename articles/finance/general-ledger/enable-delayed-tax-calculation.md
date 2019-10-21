---
title: Aktivera fördröjd momsberäkning i journal
description: Det här avsnittet innehåller information om hur du använder funktionen **Aktivera fördröjd momsberäkning i journal** för att förbättra momsberäkningsresultatet när volymen för journalrader är mycket stor.
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
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179928"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a>Aktivera fördröjd momsberäkning i journal
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Det här avsnittet innehåller information om hur du använder funktionen **Aktivera fördröjd momsberäkning i journal** för att förbättra momsberäkningsresultatet när volymen för journalrader är mycket stor.

Aktuellt momsberäkningsbeteende i journalen aktiveras realtid när en användare uppdaterar fält som är relaterade till moms, t.ex. momsgrupp eller artikelmomsgrupp. Alla uppdateringar på journalradnivå kommer att omberäkna skattebelopp på alla journalrader. Den hjälper användaren att visa det beräknade momsbeloppet i realtid, men det kan också leda till prestandaproblem om volymen på journalraderna är mycket stor.

Den här funktionen är ett alternativ till att fördröja momsberäkningen för att lösa prestandaproblem. Om den här funktionen är aktiverad kommer momsbeloppet endast att beräknas när användaren klickar på kommandot "moms" eller bokför journalen.

Användaren kan aktivera/inaktivera parametern på tre nivåer:
- Efter juridisk person
- Per journalnamn
- Per journalrubrik

Systemet kommer att ta parametervärdet för journalrubriken som slutgiltigt. Parametervärde i journalrubriken hämtas som standard från journalnamnet. Journal namnets parametervärde visas som standard från redovisningsparametern när journalnamnet skapas.

Fälten "faktiskt momsbelopp" och "beräknat momsbelopp" för journalen döljs om den här parametern aktiveras. Syftet är inte att förväxla användaren eftersom värdet i dessa två fält alltid kommer att visa 0 innan en användare utlöser momsberäkningen.

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a>Aktivera fördröjd momsberäkning per juridisk person

1. Gå till **Redovisning > Redovisningsinställning > Redovisningsparametrar**.
2. Klicka på **Moms**.
3. Under snabbfliken **allmän** hittar du parameter **fördröjd momsberäkning**, aktivera/inaktivera den

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a>Aktivera fördröjd momsberäkning per journalnamn

1. Gå till **Redovisning > Journalkonfigurering > Journalnamn**.
2. Under snabbfliken **allmän** hittar du parameter **fördröjd momsberäkning**, aktivera/inaktivera den

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a>Aktivera fördröjd momsberäkning per journal

1. Gå till **Redovisning > Journalposter > Allmänna journaler**.
2. Klicka på **Ny**.
3. Välj ett journalnamn.
4. Klicka på **Inställningar**.
5. Hitta parameter **fördröjd momsberäkning**, aktivera/inaktivera den

![](media/delayed-tax-calculation-journal-header.png)
