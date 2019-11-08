---
title: Ställ in kategorier för huvudkonto
description: Det här avsnittet innehåller information om hur du ställer in kategorier för huvudkonto i Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8e2ba1d900f5d87a76fa93bf53f2970320e7d84c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186013"
---
# <a name="set-up-main-account-categories"></a>Ställ in kategorier för huvudkonto

[!include [task guide banner](../../includes/task-guide-banner.md)]

Det här avsnittet innehåller information om hur du ställer in kategorier för huvudkonto. Huvudkontokategorier används för standardrapporterna i ekonomisk rapportering och i Power BI. DU kan byta namn på men inte ta bort huvudkontokategorier som skapats som standard. Ytterligare kontokategorier kan skapas och användas för rapporterings- och analysändamål. I det här avsnittet används demonstrationsföretaget USMF.

## <a name="create-a-main-account-category"></a>Skapa en huvudkontokategori
1. I Navigeringsfönster gå till **Moduler > Redovisning > Kontoplan > Konton > Huvudkontokategorier**.
2. Välj **Ny**.
3. Ange ett unikt namn i fältet **Huvudkontokategori**.
4. I fältet **Beskrivning** anger du en beskrivning av huvudkontokategorin.
5. I fältet **Huvudkontotyp** väljer du den huvudkontotyp som ska länkas till kategorin.

## <a name="link-main-accounts-to-account-category"></a>Länka huvudkonton till kontokategori
1. Klicka på **Länka huvudkonton**.
2. I listan väljer du de huvudkonton som ska tilldelas huvudkontokategorin genom att markera kryssrutorna i den **Länkade** kolumnen. När du tilldelar huvudkonton till en huvudkontokategori läggs kontosaldona till när kategorin används för ekonomisk rapportering och analys.  
3. Markera eller avmarkera alternativet **Länkad** för att välja huvudkontona.
4. Välj **OK**.
5. Välj **Ja**.