---
title: Blandade lagertyper vid användning av lastkajshanteringsprofil
description: För att lastkajshanteringsprofilen ska fungera effektivt måste en arbetsrubriksbrytning konfigureras först. På den här sidan förklaras hur du gör.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cc660a2f9839e886240c97a7f60d2e264653074a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477616"
---
# <a name="inventory-types-are-being-mixed-when-using-a-dock-management-profile"></a>Lagertyper blandas vid användning av en lastkajshanteringsprofil

## <a name="symptoms"></a>Symtom

Du använder *policyer för leveranskonsolidering*. Du har ställt in en *lastkajshanteringsprofil* för en *platsprofil*, men när arbete skapas blandas lagertyperna på den slutliga platsen.

## <a name="resolution"></a>Lösning

Dockhanteringsprofiler kräver att arbetet delas upp i förväg. Med andra ord förväntar sig dockhanteringsprofilen att en arbetsrubrik inte har flera platser.

För att dockhanteringsprofilen ska fungera effektivt måste en arbetsrubriksbrytning ställas in.

I det här exemplet konfigureras vår lastkajshanteringsprofil så att **Lagertyper som inte ska blandas** ställs in på *Leverans-ID* och vi ställer in en arbetsrubriksbrytning för det:

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.
1. Välj vilken **arbetsordertyp** du vill redigera (t.ex. *inköpsorder*).
1. Välj arbetsmallen som du vill redigera.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. Öppna fliken **Sortering** och lägg till en rad med följande inställningar:
    - **Tabell** - *Tillfälliga arbetstransaktioner*
    - **Härlett register** - *Tillfälliga arbetstransaktioner*
    - **Fält** - *leverans-ID*
1. Välj **OK**.
1. Du går tillbaka till sidan **Arbetsmallar**. Klicka på **Arbetsuppgiftshuvudet delas** i åtgärdsfönstret.
1. I åtgärdsfönstret väljer du **Redigera**.
1. Markera kryssrutan som är kopplad till **fältnamnet** *leverans-ID*.
1. Klicka på **Spara** i åtgärdsfönstret.
