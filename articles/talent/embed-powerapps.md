---
title: Bädda in PowerApps-appar i Dynamics 365 - Core HR
description: Det här avsnittet beskriver hur du löser problemet där PowerApps menyalternativ har försvunnit från modulen Systemadministration.
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
ms.openlocfilehash: 4fbc24c5ceb73389b84b125eb942ac31757928aa
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008440"
---
# <a name="embed-powerapps-apps-in-core-hr"></a>Bädda in appar för PowerApps i Core HR

[!include [banner](includes/banner.md)]

**Utleverans**

**PowerApps** menyalternativ har försvunnit från modulen **Systemadministration**.

**Orsak**

Designen för användargränssnittet (UI) har ändrats och Microsoft PowerApps ingår nu i standardanpassningsmodellen.

**Upplösning**

Sättet som PowerApps-appar bäddas in har ändrats. PowerApps-appar läggs nu till i anpassningsmodellen. Du kan lägga till PowerApps-appar för nästan alla sidor i Microsoft Dynamics 365 Talent.

För detaljerad information om hur du bäddar in en PowerApps-app i Talent finns i [Bädda in PowerApps-appar](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Alla PowerApps-användare som bäddar in appar innan ändringen ska uppgraderas till den nya modellen.

Knappen **PowerApps** är i det övre högra hörnet på nästan varje sida i Talent. Du kan använda den här knappen för att infoga en PowerApps-app.

Här är ett exempel:

1. Gå till **Personalhantering \> Länkar \> Arbetare \> Medarbetare**.
2. Välj knappen **PowerApps** och välj sedan **Infoga en PowerApp**.

    ![PowerApps-knapp](media/png.png)

3. Fyll i fälten i dialogrutan **Infoga en PowerApp**.

    ![Infoga en PowerApp-dialogruta](media/insert-powerapp.png)

Följ alternativt dessa steg.

1. På sidans åtgärdsfönster, på fliken **Alternativ** i gruppen **Anpassa**, välj **Anpassa detta formulär**.

    ![Anpassa grupp på fliken Alternativ](media/options.png)

    Verktygsfält för anpassning visas.

2. I verktygsfältet, välj **Infoga \> PowerApp**.

    ![Infoga en PowerApps-app med hjälp av verktygsfältet för anpassning](media/powerapp-bar.png)
