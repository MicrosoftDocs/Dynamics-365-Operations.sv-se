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
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d53181d63f7b362662d993e21671e9b685b5dfe
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968437"
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
