---
title: Skapa en ursprunglig budget och sedan återföra preliminära budgetposter i den offentliga sektorn
description: När du skapar en ursprunglig budgetpost och använder budgetmodellen och dimensionsvärden som innehåller preliminära budgetbelopp, kan de preliminära budgetbeloppen återföras.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9d1c34ac2bd94196b7bad599e9aca7ed942ae9c8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "344948"
---
# <a name="create-an-original-budget-and-then-reverse-preliminary-budget-entries-in-the-public-sector"></a>Skapa en ursprunglig budget och sedan återföra preliminära budgetposter i den offentliga sektorn

[!include [task guide banner](../../includes/task-guide-banner.md)]

När du skapar en ursprunglig budgetpost och använder budgetmodellen och dimensionsvärden som innehåller preliminära budgetbelopp, kan de preliminära budgetbeloppen återföras. Den här proceduren har skapats med hjälp av data för demoföretaget PSUS i partitionen för den offentliga sektorn.

1. Gå till Budgetering > Budgetregisterposter.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Budgetmodell.
4. Hitta och markera önskad post i listan.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Budgetkod.
6. Klicka på Ursprunglig budget i listan.
7. Klicka på Spara.
8. Klicka på Lägg till rad.
9. Valfritt: om du vill ändra datumet från det i rubriken, ange ett annat datum. Detta datum bestämmer vilken räkenskapsperiod budgeten ska registreras i.
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kontostruktur.
11. Hitta och markera önskad post i listan.
12. Ange önskade värden i fältet Dimensionsvärden.
13. I fältet Belopp, ange ett tal.
14. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.
15. Klicka på länken på den valda raden i listan.
16. Klicka på Spara.
17. Klicka på Uppdatera budgetsaldon.
    * Valfritt: du kan välja alternativet för att återföra preliminära budgetposter. Observera att du kan återföra alla preliminära budgetposter eller endast de preliminära budgetposter som har den budgetkod som du anger.  
    * Du kan göra ytterligare val genom att klicka på upplåsningsikonen högst upp på skärmen.  
18. Klicka på Uppdatera.

