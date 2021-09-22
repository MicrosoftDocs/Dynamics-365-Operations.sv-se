---
title: Du hittar inte listrutan Arbetsflöde för lagerjournaler.
description: Du hittar inte listrutan Arbetsflöde på journalsidan, eller att relaterade arbetsflödesåtgärder inte är tillgängliga
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8b2772a75c2388f4d78a459f9dfb72ad7c1be4ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477614"
---
# <a name="you-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>Du hittar inte listrutan Arbetsflöde för lagerjournaler.

## <a name="symptoms"></a>Symtom

Du hittar inte listrutan **Arbetsflöde** på journalsidan, eller att relaterade arbetsflödesåtgärder inte är tillgängliga.

Det här problemet kan uppstå av tre orsaker, som beskrivs i följande avsnitt.

## <a name="resolution-1"></a>Lösning 1

Om problemet gäller för alla användare kan det bero på att arbetsflödet för godkännande inte har tilldelats journalnamnet. Gör så här om du vill åtgärda problemet.

1. Gå till **Lagerhantering &gt; Inställningar &gt; Journalnamn &gt; Lager**.
1. Välj ett journalnamn i listfönstret för att öppna inställningarna.
1. På snabbfliken **allmänt** anger du alternativet **Godkännandearbetsflöde** till *Ja*. Om du uppmanas att bekräfta ändringen väljer du **Ja**.
1. I fältet **Arbetsflöde** välj det arbetsflöde du vill använda för det valda journalnamnet.

## <a name="resolution-2"></a>Lösning 2

Om det används anpassad kod i arbetsflödet kan problem uppstå när du har uppgraderat systemet. I journalarbetsflödet kan till exempel knappen **Skicka** vara gråtonad så att du inte kan välja den för att godkänna en överföring.

Om knappen **Skicka** är gråtonad kanske arbetsflödet har anpassats, vilket innebär att metoden för arbetsflödet, `canSubmitToWorkflow()` i `FormDataUtil`, utökats. Du åtgärdar problemet genom att ändra sättet som du utökar metoden för `canSubmitToWorkflow()` för att använda strukturen i följande exempel.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

## <a name="resolution-3"></a>Lösning 3

Om problemet endast gäller ett fåtal specifika användare kanske dessa användare inte har de säkerhetsprivilegier som krävs för att köra arbetsflödesåtgärder på lagerjournaler. Kontrollera att varje berörd användare har säkerhetsprivilegiet *Underhåll arbetsflöde för lagerjournal*. Som standard tilldelas det här privilegiet ett uppdrag som har samma namn och uppdraget tillämpas rollerna *Lagerarbetare* och *Lagerchef*.
