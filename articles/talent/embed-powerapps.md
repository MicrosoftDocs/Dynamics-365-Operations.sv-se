---
title: Bädda in Power Apps-appar i Dynamics 365 Human Resources
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
ms.openlocfilehash: 8275a8a7c68fa13d6b9880c4c411deaa2dcbb998
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462549"
---
# <a name="embed-power-apps-apps-in-dynamics-365-human-resources"></a>Bädda in Power Apps-appar i Dynamics 365 Human Resources

**Utleverans**

**Power Apps** menyalternativ har försvunnit från modulen **Systemadministration**.

**Orsak**

Designen för användargränssnittet (UI) har ändrats och Microsoft Power Apps ingår nu i standardanpassningsmodellen.

**Upplösning**

Sättet som Power Apps bäddas in har ändrats. Power Apps läggs nu till i anpassningsmodellen. Du kan lägga till Power Apps för nästan alla sidor i Microsoft Dynamics 365 Talent.

För detaljerad information om hur du bäddar in en Power Apps i Talent finns i [Bädda in Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Alla Power Apps-användare som bäddar in appar innan ändringen ska uppgraderas till den nya modellen.

Knappen **Power Apps** är i det övre högra hörnet på nästan varje sida i Talent. Du kan använda den här knappen för att infoga appar.

Här är ett exempel:

1. Gå till **Personalhantering \> Länkar \> Arbetare \> Medarbetare**.
2. Markera **Power Apps**-knappen och välj sedan **Lägg till en app från Power Apps**.

    ![Power Apps-knapp](media/png.png)

3. Slutför fälten i dialogrutan **Lägg till en app från Power Apps**.

    ![Dialogrutan lägg till en app från Power Apps](media/insert-powerapp.png)

Följ alternativt dessa steg.

1. På sidans åtgärdsfönster, på fliken **Alternativ** i gruppen **Anpassa**, välj sidan **Anpassa detta formulär**.

    ![Anpassa grupp på fliken Alternativ](media/options.png)

    Verktygsfält för anpassning visas.

2. På verktygsfältet, välj **Lägg till en app från Power Apps**.

    ![Lägg till en app från Power Apps med hjälp av verktygsfältet för anpassning](media/powerapp-bar.png)
