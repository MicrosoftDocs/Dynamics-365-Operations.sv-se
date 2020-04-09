---
title: Konfigurera koncernintern projektfakturering
description: Det här avsnittet visar hur du ställer in projektfakturering mellan två företag i din organisation.
author: KimANelson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 31dbae2d37aefe1841fe85cb6caf185c78596e55
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144289"
---
# <a name="configure-intercompany-project-invoicing"></a>Konfigurera koncernintern projektfakturering

[!include [banner](../../includes/banner.md)]

Det här avsnittet visar hur du ställer in projektfakturering mellan två företag i din organisation. I den här uppgiften används datauppsättningen USSI.

1. I navigeringsfönstret, gå till **Moduler > Leverantörsreskontra > Leverantörer > Alla leverantörer**.
2. Sök efter och markera önskad post i listan **Alla leverantörer**.
3. Välj **Allmänt** i åtgärdsfönstret.
4. Välj **Koncernintern**.
5. Ange **Aktiv** som **Ja** för att aktivera koncernintern handel.
6. Ange eller välj ett värde i fältet **Kundföretag**.
7. Ange eller välj ett värde i fältet **Mitt konto**.
8. Välj **Spara**.
9. Stäng sidorna om du vill gå tillbaka till startsidan.
10. I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Parametrar för projekthantering och redovisning**.
11. Välj fliken **Koncernintern**.
12. Flytta reglaget till **Ja** för att aktivera koncernintern resursplanering och tidrapporter.
13. Markera vald rad i listan.
14. Välj **Ny**.
15. Ange eller välj ett värde i fältet **Lånande juridisk person**.
16. Välj kryssrutan **Upplupen intäkt**.
17. Ange eller välj ett värde i fältet **Standardkategori för tidrapport**.
18. Ange eller välj ett värde i fältet **Standardkategori för utgift**.
19. Välj **Spara**.
20. Stäng sidan.
21. I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Bokföring > Inställning av redovisningsbokföring**.
22. Välj ett alternativ i fältet **Huvudbokskontotyper**.
23. Välj **Ny**.
24. Ange önskade värden i fältet **Huvudkonto** för den nya raden.
25. Välj **Spara**.
26. Stäng sidan.
27. I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Inställningar > Priser > Internpris**.
28. Välj **Ny**.
29. Ange ett datum i fältet **Giltighetsdatum**.
30. Ange eller välj ett värde i fältet **Lånande juridisk person**.
31. Välj ett alternativ i fältet **Modell för överföringspris**.
32. Ange ett nummer i fältet **Pris**.
33. Välj **Spara**.

