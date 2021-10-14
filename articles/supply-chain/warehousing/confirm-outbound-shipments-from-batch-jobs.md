---
title: Bekräfta utgående leveranser från batchjobb
description: I det här avsnittet beskrivs hur du ställer in ett batchjobb som automatiskt bekräftar utgående överföringsorder leveranser för laster som är redo att skickas.
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
ms.openlocfilehash: d47b88fcc5e25fc85377b52fa9832916a4bb2217
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572395"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Bekräfta utgående leveranser från batchjobb

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in ett batchjobb som automatiskt bekräftar utgående överföringsorder leveranser för laster som är redo att skickas. Det batchjobb som beskrivs här gäller bara för överföring av orderleveranser, inte för försäljningsorder.

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a>Aktivera funktionen Bekräfta utgående leveranser från batchjobb

Innan du kan använda den här funktionen måste du aktivera den i ditt system. Administratörer kan använda sidan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas som:

- **Modul** - *Lagerstyrning*
- **Funktionens namn** - *Bekräfta utgående leveranser från batchjobb*

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