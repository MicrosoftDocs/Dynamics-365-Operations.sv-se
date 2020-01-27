---
title: Bädda in Power Apps-appar i Dynamics 365 - Core HR
description: Det här avsnittet beskriver hur du löser problemet där Microsoft Power Apps menyalternativ har försvunnit från modulen Systemadministration.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b1dd1756be349d85af8e6d7159623a2a95e75526
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898722"
---
# <a name="embed-power-apps-apps-in-dynamics-365---core-hr"></a>Bädda in Power Apps-appar i Dynamics 365 - Core HR

**Utleverans**

**Power Apps** menyalternativ har försvunnit från modulen **Systemadministration**.

**Orsak**

Designen för användargränssnittet (UI) har ändrats och Microsoft Power Apps ingår nu i standardanpassningsmodellen.

**Upplösning**

Sättet som Power Apps bäddas in har ändrats. Power Apps läggs nu till i anpassningsmodellen. Du kan lägga till Power Apps för nästan alla sidor i Microsoft Dynamics 365 Talent.

För detaljerad information om hur du bäddar in en Power Apps i Talent finns i [Bädda in Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Alla Power Apps-användare som bäddar in appar innan ändringen ska uppgraderas till den nya modellen.

Knappen **Power Apps** är i det övre högra hörnet på nästan varje sida i Talent. Du kan använda den här knappen för att infoga en Power Apps.

Här är ett exempel:

1. Gå till **Personalhantering \> Länkar \> Arbetare \> Medarbetare**.
2. Välj knappen **Power Apps** och välj sedan **Infoga en PowerApp**.

    ![Power Apps-knapp](media/png.png)

3. Fyll i fälten i dialogrutan **Infoga en PowerApp**.

    ![Infoga en PowerApp-dialogruta](media/insert-powerapp.png)

Följ alternativt dessa steg.

1. På sidans åtgärdsfönster, på fliken **Alternativ** i gruppen **Anpassa**, välj **Anpassa detta formulär**.

    ![Anpassa grupp på fliken Alternativ](media/options.png)

    Verktygsfält för anpassning visas.

2. I verktygsfältet, välj **Infoga \> PowerApp**.

    ![Infoga en Power Apps-app med hjälp av verktygsfältet för anpassning](media/powerapp-bar.png)
