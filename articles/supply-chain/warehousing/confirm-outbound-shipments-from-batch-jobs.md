---
title: Bekräfta utgående leveranser från batchjobb
description: I denna artikel beskrivs hur du konfigurerar batchjobb som automatiskt bekräftar utgående leveranser av överföringsorder för laster som är redo att skickas.
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 00749a69b17b0064290d7b41ccb2171386716302
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875113"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Bekräfta utgående leveranser från batchjobb

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar batchjobb som automatiskt bekräftar utgående leveranser av överföringsorder för laster som är redo att skickas. Det batchjobb som beskrivs här gäller bara för överföring av orderleveranser, inte för försäljningsorder.

## <a name="turn-the-confirm-outbound-shipments-from-batch-jobs-feature-on-or-off"></a>Aktivera eller inaktivera funktionen Bekräfta utgående leveranser från batchjobb

För att kunna använda de funktioner som beskrivs i denna artikel måste funktionen *Bekräfta utgående leveranser från batchjobb* vara aktiverad för ditt system. Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.25 kan administratörer aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Bekräfta utgående leveranser från batchjobb* i arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="process-outbound-shipments"></a>Bearbeta utgående leveranser

Så här ställer du in ett tidsplanerat batchjobb för att köra bekräftelse av utgående leverans för laster som är klara att levereras:

1. Gå till **lagerstyrning \> periodiska uppgifter \> bearbeta utgående leveranser**.
1. Dialogrutan **Bekräfta leverans** öppnas. På snabbfliken **Poster att inkludera**, välj **Filter**.
1. Dialogrutan frågeredigeraren öppnas. På fliken **intervall**, lägg till en rad med följande värden:
    - **Register** - *Laster*
    - **Härledda register** - *Laster*
    - **Fält** - *Laststatus*
    - **Kriterier** - *Lastad*
1. Välj **OK** om du vill gå tillbaka till dialogrutan **Bekräfta leverans**.
1. På snabbfliken **Kör i bakgrunden** ange **Batchbearbetning** till **Ja**.
1. På snabbfliken **kör i bakgrunden** väljer du **återkommande**.
1. Dialogrutan **Definiera återkommande** öppnas. Ange det körschema som behövs för ditt företag.
1. Välj **OK** om du vill gå tillbaka till dialogrutan **Bekräfta leverans**.
1. Välj **OK** i dialogrutan **Bekräfta leverans** för att lägga till batchjobbet i batchkön.

Mer information finns i [Översikt över batchbearbetning](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]