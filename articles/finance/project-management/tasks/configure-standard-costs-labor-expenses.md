---
title: Konfigurera standardkostnader för arbetskraft och utgifter
description: Det här avsnittet visar hur du ställer in standardkostnader för arbete och utgifter för ett projekt.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51bbe52d70bae11cb0c95e9544f951f0fcc605f5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140103"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Konfigurera standardkostnader för arbetskraft och utgifter

[!include [banner](../../includes/banner.md)]

Det här avsnittet visar hur du ställer in standardkostnader för arbete och utgifter för ett projekt. I den här uppgiften används datauppsättningen USSI.

1. I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Priser > Självkostnad (timme)**.
2. Välj **Ny**.
3. Ange ett datum i fältet **Giltighetsdatum**.
4. Ange ett värde i fältet **Självkostnad**. Du kan ställa in ett standardsjälvkostnadspris för projektkategorin, eller också kan du ställa in ett självkostnadspris efter medarbetarnummer, projektnummer, kategori, datum eller någon kombination av dessa. Det självkostnadspris som används är det mest detaljerade.  
5. Välj **Spara**.
6. I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Priser > Försäljningspris (timme)**.
7. Välj **Ny**.
8. Ange ett datum i fältet **Giltighetsdatum**.
9. Välj ett alternativ i fältet **Gäller för**.
10. Ange ett nummer i fältet **Pris**. Du kan ställa in ett standardförsäljningspris för timtransaktioner eller för en projektkategori. Du kan också ställa in försäljningspriser efter medarbetarnummer, projektnummer, kategori, transaktionsdatum eller valfri kombination av dessa. Det verkliga försäljningspriset, som används när en medarbetare registrerar en transaktion i timjournalen, är försäljningspriset med den högsta detaljnivån. Om till exempel både ett allmänt försäljningspris och ett medarbetarspecifikt försäljningspris har angivits, används automatiskt det medarbetarspecifika försäljningspriset.  
11. Välj **Spara**.
12. Stäng sidan.
13. I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Priser > Självkostnad (utgift)**.
14. Välj **Ny**.
15. Ange ett datum i fältet **Giltighetsdatum**.
16. Ange ett värde i fältet **Självkostnad**. Flera fält kan fyllas i, men detta är det som krävs för att spara posten.  
17. Välj **Spara**.
18. I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Priser > Försäljningspris (utgift)**.
19. Välj **Ny**.
20. Ange ett datum i fältet **Giltighetsdatum**.
21. Välj ett alternativ i fältet **Gäller för**.
22. Ange ett nummer i fältet **Pris**. Det verkliga försäljningspriset, som används när en medarbetare registrerar transaktionerna i en utgiftsjournal, är försäljningspriset med den högsta detaljnivån. Om till exempel både ett allmänt försäljningspris och ett medarbetarspecifikt försäljningspris har angivits, används det medarbetarspecifika försäljningspriset.  
23. Välj **Spara**.

