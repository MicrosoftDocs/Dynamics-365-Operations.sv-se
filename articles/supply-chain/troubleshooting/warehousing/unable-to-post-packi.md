---
title: Kan inte bokföra följesedel för en stoppad försäljningsorderrad
description: Du kan inte bokföra följesedel för en stoppad försäljningsorderrad
author: smithanataraj
ms.date: 03/07/2022
ms.topic: article
ms.search.form: WHSLoadTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mfp
ms.search.validFrom: 2022-03-07
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 115cfe79e075eb36f73203818acdbb5e31fc0bad
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462860"
---
# <a name="cant-post-packing-slip-for-a-stopped-a-sales-order-line"></a>Kan inte bokföra följesedel för en stoppad försäljningsorderrad

Felkod: SYS13203

## <a name="symptoms"></a>Symtom

När du försöker skicka en följesedel för en last, visar systemet följande felmeddelande:

> Det går inte att bokföra följesedel när en försäljningsorderrad stoppas efter att den utgående försändelsen A-kvantitet har bekräftats går inte att plocka.

## <a name="cause"></a>Orsak

En eller flera relaterade försäljningsorderrader kan stoppas, vilket innebär att systemet förhindrar att försäljningsordern bearbetas ytterligare. Det innebär bland annat att systemet inte bokför en följesedel för ordern.

Exempelvis kan en användare ha beslutat stoppa en eller flera orderrader eftersom kunden ringt tillbaka och annullerat sin order. Om den utgående leveransen redan har bekräftats har dock försändelsen som innehåller försäljningsordern redan fysiskt lämnat lagerstället, vilket innebär att det inte har någon effekt att stoppa försäljningsorderraderna. Eftersom det inte längre går att fysiskt stoppa försändelsen kan du eventuellt ta bort försändelseraderna så att du kan bokföra följesedeln. Du måste sedan hantera den annullerade ordern som en retur.

## <a name="resolution"></a>Lösning

Om du vill kunna bokföra följesedeln ser du till att inga relevanta försäljningsorderrader stoppas genom att du utför följande steg.

1. Gå till **Alla försäljningsorder \> Försäljning och marknadsföring \> Alla försäljningsorder**.
1. Sök och öppna den försäljningsorder som du har problem med.
1. På snabbfliken **Försäljningsorderrader** väljer du en försäljningsorderrad.
1. På fliken **Raddetaljer**, öppna fliken **Allmänt** och kontrollera att fältet **Stoppat** har satts till *Nej*.
1. Fortsätt arbeta tills alla relevanta försäljningsrader inte längre har stoppats.
1. Försök igen att bokföra följesedeln för beläggnings- eller försäljningsordern.
