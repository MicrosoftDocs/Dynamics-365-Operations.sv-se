---
title: Leverantörsinställningar som läggs till för hemtagningskostnad
description: I det här avsnittet beskrivs de nya fält som läggs till på den befintliga leverantörssidan när du aktiverar modulen hemtagningskostnad. Du använder dessa fält när du vill ställa in de leverantörer som du ska använda tillsammans med funktionerna för hemtagningskostnader.
author: sherry-zheng
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 8cc0622cd761a671ebb88addc36b777cfefb7dc7
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500920"
---
# <a name="vendor-settings-added-for-landed-cost"></a>Leverantörsinställningar som läggs till för hemtagningskostnad

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

När du aktiverar modulen **Hemtagningskostnad** läggs flera nya fält till på den befintliga sidan **Leverantörer**. Du använder dessa fält när du vill ställa in de leverantörer som du ska använda tillsammans med funktionerna för hemtagningskostnader.

Om du vill ställa in relevanta fält **Anskaffning och källa \> Leverantörer \> Alla leverantörer**. Öppna en befintlig leverantör eller skapa en ny leverantör och markera sedan snabbflikarna **Diverse information**. Alla nya fält som modulen **Hemtagningskostnad** lägger till visas under rubriken **Färder**. Följande register beskriver fälten.

| Fält | beskrivning |
|---|---|
| Leveranstyp | <p>Välj leverantörens roll i relation till hemtagningskostnad:</p><ul><li>**Ingen** – Leverantören har ingen specifik roll som är relaterad till hemtagningskostnad. Det här värdet är standardinställningen, eftersom de flesta leverantörer troligen inte har någon specifik roll.</li><li>**Transportföretag** – Leverantören är ett transportföretag. Leverantörer som har den här leveranstypen kan väljas i fältet **Transportföretag** på sidan **Färder**.</li><li>**Tullombud** – Leverantören är ett tullombud. Leverantörer som har den här leveranstypen kan väljas i fältet **Tullombud** på sidan **Folio**.</li><li>**Agent** – Leverantören är en agent. Leverantörer som har den här leveranstypen kan väljas i fältet **Agent** på sidorna **Leverantörer** och **Inköpsorder**.</li></ul> |
| Kostnadstypsgrupp | Tilldela leverantören till en kostnadstypgrupp i syfte att välja [automatiska kostnader](auto-cost-setup.md). |
| Från hamn | Välj ursprungsport för färden. |
| Handläggare | Standardagenten när inköp görs från leverantören. |
| Leverantör för importkostnadsredovisning | <p>Indikera om leverantören är en leverantör av typen Hemtagningskostnad.</p><p>**Tips:** Du kan använda det här fältet tillsammans med säkerhet på postnivå för att begränsa de inköpsorder som visas när en färd skapas.</p> |
| Speditör | Välj det standardleveransföretag som används när inköpsorder skapas för leverantören. |
| Leverantör av tjänster | Ange om leverantören är en leverantör av tjänster. |
| Över-/undertoleransgrupp | Välj standardgrupp för över-/undertolerans för leverantören. |
