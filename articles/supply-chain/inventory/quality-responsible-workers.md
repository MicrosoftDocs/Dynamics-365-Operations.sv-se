---
title: Medarbetare som ansvarar för godkännande av avvikelser
description: I detta ämne beskrivs hur du konfigurerar arbetare som ansvarar för godkännande av avvikelser.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b764baf0983dbca75d52ea9cdd063cebda80a08d39cf3a5c929f15858e2597c1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768177"
---
# <a name="workers-responsible-for-approving-nonconformances"></a>Medarbetare som ansvarar för godkännande av avvikelser

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs hur du konfigurerar arbetare som ansvarar för godkännande av avvikelser.

Avvikelser måste godkännas innan användarna kan börja registrera information som korrigeringar eller funktioner. Innan användarna kan godkänna eller avvisa avvikelseer måste deras användar-ID (användarpost) länkas till en medarbetarpost. Om du vill kan du även konfigurera medarbetare som ansvarar för kvalitet och sedan tillåta en medarbetare att godkänna arbete på uppdrag av en annan medarbetare.

## <a name="enable-a-user-for-nonconformance-processing"></a>Gör det möjligt för en användare att bearbeta avvikelser

Innan en användare kan godkänna eller avvisa avvikelseer måste du koppla deras användarpost till en medarbetarpost. Godkännandefälten kan sedan ställas in automatiskt, och den aktuella användaren kan automatiskt fyllas i för tidrapporten. Innan användaren kan använda dokumentanteckningarna måste du aktivera dokumenthantering bland deras användaralternativ.

1. Gå till **Systemadministration \> Användare \> Användare**.
1. Sök efter och öppna den användare som ska kunna godkänna eller avvisa avvikelser.
1. Ställ in fältet **Person** som namnet på den medarbetare som är relaterad till den aktuella användarposten.
1. I åtgärdsfönstret väljer du **Användaralternativ**.
1. På sidan **Alternativ** för den aktuella användarposten, på fliken **Inställningar**, anger du alternativet **Aktivera dokumenthantering** som *Ja*.
1. Stäng sidorna.

## <a name="define-workers-that-are-responsible-for-quality"></a>Definiera medarbetare som ansvarar för kvalitet

1. Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Medarbetare med kvalitetsansvar**.
2. Klicka på **Ny** i åtgärdsfönstret.
3. I fältet **Medarbetare** väljer du den medarbetare som anger kvalitetsdata.
4. I fältet **Ansvarig medarbetare** väljer du den medarbetare i vars ställe den valda medarbetaren utför arbete. När avvikelser skapas och uppdateras anges denne medarbetare som standard i fälten **Medarbetare**.

## <a name="additional-resources"></a>Ytterligare resurser

- [Kvalitetshantering – översikt](quality-management-processes.md)
- [Aktivera kvalitets- och avvikelsehantering](enable-quality-management.md)
- [Kvalitetsavgifter](quality-charges.md)
- [Karantänzoner för avvikelser](quality-quarantine-zones.md)
- [Diagnostyper för avvikelser](quality-diagnostic-types.md)
- [Kvalitetsavgifter för avvikelser](quality-charges.md)
- [Funktioner för avvikelser](quality-operations.md)
- [Kvalitetsstyrning för lagerprocesser](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
