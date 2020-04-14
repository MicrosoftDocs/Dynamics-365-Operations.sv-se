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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e0a015283064af2287013bccc065b4467a308c5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144799"
---
# <a name="set-up-main-account-categories"></a>Ställ in kategorier för huvudkonto

[!include [banner](../../includes/banner.md)]

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
