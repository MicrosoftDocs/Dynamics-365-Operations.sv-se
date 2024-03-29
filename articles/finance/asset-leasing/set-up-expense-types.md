---
title: Konfigurera utgiftstyper
description: Den här artikeln beskriver hur du konfigurerar utgiftstyper i Leasing av tillgångar.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseExpenseTypeTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9978041059437d5d3556236c7ac02c00db93f933
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908050"
---
# <a name="set-up-expense-types"></a>Konfigurera utgiftstyper

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver hur du konfigurerar utgiftstyper i Leasing av tillgångar. Kostnader som inte representeras av betalningsplanen kallas för *utgiftskostnader*. Exempel på dessa kostnader är fastighetsskatter, allmänna underhållskostnader och försäkringskostnader.

## <a name="add-an-administrative-expense-type"></a>Lägga till en administrativ utgiftstyp

1. Gå till **Leasing av tillgångar \> Konfigurera \> Utgiftstyper**.
2. Välj **Ny**.
3. Ange den nya utgiftstypen och en beskrivning i lämpliga fält.

## <a name="assign-accounts-to-administrative-costs"></a>Tilldela konton till administrationskostnader

Därefter ska du koppla konton till utgiftstyperna. De här kontona kommer att debiteras när poster för utgiftsplaner bokförs. Motkontot anges på raderna för **betalningsplanen för verkställighetskostnad** för varje leasing.

1. Gå till **Leasing av tillgångar \> Konfigurera \> Parametrar för tillgångsleasing**.
2. Välj utgiftstypen på fliken **Konton**, på snabbfliken **Verkställighetskostnader**, i fältet **Utgiftstyp** .
3. Markera **Lägg till**.
4. I **Boktyp** väljer du den boktyp som ska länkas till administrationskostnaderna.

    > [!NOTE]
    > Flera boktyper kan kopplas till samma utgiftskonto.

5. I fältet **Kontokod** anger du vilka leasingar som boken ska gälla för:

    - **Alla** – Boken gäller för alla leasingar.
    - **Grupp** – Boken gäller för en specifik grupp med leasingar.
    - **Tabell** – Boken gäller för specifika leasingar.

6. Om du har valt **Grupp** eller **Tabell** i fältet **Kontokod** väljer du ett kontonummer eller gruppnummer i fältet **Konto/gruppnummer**.
7. Välj huvudkonto för finansiell leasing och huvudkonto för operationell leasing i lämpliga fält.

När du har utfört de här stegen kan du lägga till utgifter via raderna för **betalningsplanen för verkställighetskostnad** på sidan **Leasingdetaljer** för en vald leasing. Du kan också lägga till utgifter när du skapar en ny leasing.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
