---
title: Skapa en inköpsorder som omfattas av budget
description: Använd den här proceduren för att skapa en inköpsorder som ska kontrolleras med avseende budget.
author: JennySong-SH
ms.date: 06/15/2020
ms.topic: business-process
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa9777ad3aa487dfb558879335f93f347b8ac749
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016200"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>Skapa en inköpsorder som omfattas av budget

[!include [banner](../../includes/banner.md)]

Använd den här proceduren för att skapa en inköpsorder som ska kontrolleras med avseende budget.

## <a name="review-the-budget-control-configuration"></a>Granska budgetkontrollkonfigurationen

1. Gå till **Budgetering > Inställningar > Budgetkontroll > Budgetkontrollkonfiguration**.
1. Välj fliken **Budgetmedel är tillgängliga**.
1. Välj på fliken **Dokument och journaler**.
1. Välj på fliken **Definiera budgetkontrollregler**.
1. Välj på fliken **Definiera budgetgrupper**.
1. Stäng sidan.

## <a name="create-a-purchase-order"></a>Skapa en inköpsorder

1. Gå till **Anskaffning och källa > Inköpsorder > Alla inköpsorder**.
1. Välj **Ny**.
1. I **leverantörskonto** fält, ange eller välj ett värde.
1. Expandera **Allmänt** snabbflik.
1. I fältet **Redovisningsdatum** ställer du in datumet.
1. Välj **OK** för att stänga dialogrutan och öppna din nya inköpsorder.
1. På snabbfliken **Inköpsorderrader** markerar du **Lägg till rad** i verktygsfältet för att lägga till en ny rad och fyller sedan i raden som behövs för att lägga till en artikel på ordern.
1. På snabbflikens verktygsfält **inköpsorderraden**, välj **Ekonomi \> Distribuera belopp**.
1. I fältet **Redovisningskonto** ange ett konto.
1. Stäng sidan.

## <a name="perform-budget-checking"></a>Utför budgetkontroll

1. Fortsätt att arbeta med den inköpsorder som du just lade till en rad på.
1. På snabbflikens verktygsfält **inköpsorderrader**, välj **Ekonomi \> Utför budgetkontroll**.
1. På snabbflikens verktygsfält **inköpsorderrader**, välj **Ekonomi \> Fel eller varningar från budgetkontroll**.
1. Dialogrutan **Fel eller varningar från budgetkontroll** öppnas. Kontrollera resultaten för checken och välj **stäng** sedan dialogrutan.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]