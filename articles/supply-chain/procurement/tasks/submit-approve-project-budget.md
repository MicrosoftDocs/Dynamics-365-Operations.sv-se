---
title: Skapa och skicka in en projektbudget arbetsflöde
description: Den här proceduren visar hur du skapar och skickar in en budget för ett projekt.
author: Henrikan
ms.date: 11/22/2021
ms.topic: article
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f410d824be717537e6dfb5dbd8b71ff7d992e0a
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/23/2021
ms.locfileid: "7860435"
---
# <a name="create-and-submit-a-project-budget-workflow"></a>Skapa och skicka in en projektbudget arbetsflöde

[!include [banner](../../includes/banner.md)]

När du skapar en projektbudget kan du ange uppskattade intäkter och kostnader för ett projekt, och sedan använda värden för att styra faktiska projekttransaktioner. Projektbudgetering kräver måste alla ursprungliga budgetar och ändringar skickas till ett projektarbetsflöde för godkännande. Arbetsflödet ökar din kontroll över budgeteringen och skapar en post för ändringshistorik. Efter att du har [skapa ett projekt](/dynamicsax-2012/appuser-itpro/create-a-project), använd denna procedur för att skapa och skicka in budgeten.

1. Gå till **Moduler** > **Projekthantering och redovisning** > **Projekt** > **Alla projekt**.
1. Välj projektet från projektlistan.
1. I projektets detaljsida, välj **Plan**.
1. Under gruppen **Budget**, välj **Projektbudget**.
1. På snabbfliken **Allmänt** anger du följande information:
   - I rutan **Beskrivning** anger du ett värde.
   - Välj alternativ för **ursprunglig budget**.
   - Välj alternativ för **Resterande budget**.
1. Expandera snabbflikarna **Kostnader** och välj **Ny**. Gör följande inställningar:
   - Välj ett alternativ i fältet **Transaktionstyp**.
   - Välj en lämplig **kategori**.
   - Ange ett värde i **ursprunglig budget**.
1. Expandera snabbflikarna **Intäkter** och välj **Ny**. Gör följande inställningar:
   - Välj ett alternativ i fältet **Transaktionstyp**.
   - Välj en **kategori**.
   - Ange ett värde för **ursprunglig budget**.
1. Välj **Spara**.
1. Välj **Arbetsflöde \> Skicka in**.
1. På sidan **Granska det ursprungliga budgetarbetsflödet - Skicka** ange en **Kommentar** och välj **Skicka**.
