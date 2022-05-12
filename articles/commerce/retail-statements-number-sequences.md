---
title: Ställ in nummerserie för butiksutdrag
description: I det här avsnittet beskrivs hur du konfigurerar de nummerserier som krävs för butiksutdrag i Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: db47ca4ee8bac0d55b9a9c732183d2734bce660f
ms.sourcegitcommit: 9e1129d30fc4491b82942a3243e6d580f3af0a29
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8649222"
---
# <a name="set-up-number-sequences-for-retail-statements"></a>Ställ in nummerserie för butiksutdrag

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

I det här avsnittet beskrivs hur du konfigurerar de nummerserier som krävs för butiksutdrag i Microsoft Dynamics 365 Commerce.

Två typer av butiksutdrag används i Dynamics 365 Commerce: 

- **Transaktionsutdrag** är avsedda att skapas och bokföras med hög frekvens. De används för att bokföra alla icke-ekonomiska transaktioner i butiken till Dynamics 365 Commerce-administration. 
- **Bokslut** är avsedda att skapas och bokföras en gång per arbetsdag. De omfattar bara stängda skift från butikerna som har förts över till Commerce-administration via p-jobbet.

## <a name="configure-a-number-sequence-for-statement-posting"></a>Konfigurera en nummerserie för utdragsbokföringar

När du har slutfört inställningen av en butik måste du i Commerce-adminstration konfigurera en unik nummerserie som används för utdrag under genereringen av utdraget.

Följ de här stegen om du vill konfigurera en utdragsbokföringar i Commerce-administration.

1. Gå till **Organisationsadministration \> Nummerserier \> Nummerserier**.
1. Välj **Ny \> nummerserie** för att skapa en ny post.
1. I snabbfliken **Identifiering**, i fältet **Nummerseriekod**, anger du nummerseriekod.
1. I fältet **nummerserienamn** ange ett namn.
1. På snabbfliken **Omfångsparametrar**, i fältet **Omfång**, väljer du **Driftenhet**.
1. I fältet **Driftenhet** välj den butik som nummerserien ska användas för.
1. På snabbfliken **segment**, definiera segment.
1. På snabbfliken **Referenser** ange fältet **Område** till **Butik**.
1. Ställ in fältet **Referens** till **Utdragsnummer** och välj sedan **OK**.

    ![Snabbflikar för ID, Områdesparametrar, Segment och referenser på sidan Nummerserier.](media/retail-statements-num-seq-setup-01.png)

1. På snabbfliken **Allmänt** i avsnittet **Nummerallokering**, uppdatera fälten **Minsta** och **Största** så att de matchar längden på segment **Alfanumeriska** som du definierade snabbfliken **Segment**.
1. På snabbfliken **Prestanda** rekommenderar vi att du anger alternativet **Förallokering** till **Ja** och fältet **Antal nummer** till **25**.

    ![Snabbflikar för allmänt konto och prestanda på sidan Nummerserier.](media/retail-statements-num-seq-setup-02.png)

1. I åtgärdsfönstret, välj **Spara** för att spara dina ändringar och stänga sidan.
