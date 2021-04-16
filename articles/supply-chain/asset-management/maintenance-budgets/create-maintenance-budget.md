---
title: Skapa underhållsbudgetar
description: I det här avsnittet beskrivs hur du skapar en underhållsbudget i Tillgångshantering.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetBudgetLineAdjust, EntAssetBudget, EntAssetBudgetRecalc, EntAssetBudgetCopy, EntAssetBudgetLine, EntAssetBudgetCreate, EntAssetBudgetApprove, EntAssetBudgetCalculateActualCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b91b398c4ef864a92a5318b7e80f71a5a572844e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836768"
---
# <a name="create-maintenance-budgets"></a>Skapa underhållsbudgetar

[!include [banner](../../includes/banner.md)]

 



Underhållsbudgetar används för att ge en översikt över de förväntade kostnaderna för förebyggande underhåll. Budgetrader beräknas utifrån de rader i underhållsschemat som har ett förväntat startdatum under budgetperioden.

Underhållsbudgetar baseras på kostnadstyperna som används i Tillgångshantering: **förebyggande**, **korrigerande** och **investering**. Budgetkostnader för investeringsunderhåll inkluderas för aktiva tillgångar med ett ersättningsdatum under budgetperioden och ett relaterat ersättningsvärde. Budgetkostnader för korrigerande underhåll inkluderas om ett tidigare korrigeringsdatum ingår i budgetberäkningen. I det fallet beräknas de eventuella korrigeringskostnader från en tidigare period för samma framtida period som du beräknar underhållsbudgeten för.

## <a name="create-a-maintenance-budget"></a>Skapa en underhållsbudget

1. Välj **Tillgångshantering** \> **Förfrågningar** \> **Underhållsbudget** \> **Budget**.
2. Välj **Skapa budget**.
3. I fältet **Underhållsbudget** anger du ett budget-ID.
4. Ange en beskrivning i fältet **beskrivning**.
4. Ange start- och slutdatum för budgetperioden på snabbfliken **Period** i fälten **Från datum** och **Till datum**.
5. Om du vill inkludera korrigerande budgetkostnader som beräknas på grundval av faktiska kostnader från en tidigare period anger du i fältet **Korrigerande från datum** startdatumet för den period som dessa kostnader ska inkluderas från.
6. Beroende på vilken detaljnivå som krävs i budgeten ställer du in de relevanta alternativen på de fem snabbflikarna **Gruppera efter**.
7. Välj **OK**.
8. Välj **Budgetrader** för att öppna sidan **Budgetrader för underhåll** där du kan visa alla budgetrader som har skapats för perioden.
9. Om du vill godkänna budgeten väljer du den på sidan **Underhållsbudgetar** och väljer sedan **Godkänn**. Välj sedan **OK** i dialogrutan **Godkänn budget**. Ditt namn anges i fältet **Godkänd av** på sidan **Underhållsbudgetar**.

    > [!NOTE]
    > När du har godkänt en underhållsbudget kan du inte räkna om eller justera de relaterade raderna på sidan **Budgetrader för underhåll** om du inte först tar bort godkännandet. Om du vill ta bort godkännandet av en underhållsbudget väljer du den på sidan **Underhållsbudgetar** och väljer sedan **Godkänn**. Välj sedan **OK** i dialogrutan **Godkänn budget**.

![Underhållsbudgetar](media/01-maintenance-budgets.png)

Du kan också skapa en ny underhållsbudget genom att kopiera en befintlig budget. På sidan **Underhållsbudgetar** väljer du först budgeten som ska kopieras och sedan **Kopiera**. Den här metoden är användbar om du till exempel har skapat en budget för en månad och vill kopiera den till andra månader.

> [!NOTE]
> Underhållsbudgeten beräknar bara budgetkostnader baserat på underhållsschemarader. Om du vill beräkna faktiska kostnader för samma period kan du göra denna beräkning på sidan **Kostnadskontroll för tillgång**. 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]