---
title: Leverantörsinställningar som läggs till för hemtagningskostnad
description: I denna artikel beskrivs de nya fält som läggs till på den befintliga leverantörssidan när du aktiverar modulen hemtagningskostnad. Du använder dessa fält när du vill konfigurera de leverantörer som du ska använda tillsammans med funktionerna för hemtagningskostnader.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 84d1dee0815b036a3d411eabff49d8a08249bed3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882588"
---
# <a name="vendor-settings-added-for-landed-cost"></a>Leverantörsinställningar som läggs till för hemtagningskostnad

[!include [banner](../../includes/banner.md)]

När du aktiverar modulen **Hemtagningskostnad** läggs flera nya fält till på den befintliga sidan **Leverantörer**. Du använder dessa fält när du vill konfigurera de leverantörer som du ska använda tillsammans med funktionerna för hemtagningskostnader.

Om du vill konfigurera relevanta fält **Anskaffning och källa \> Leverantörer \> Alla leverantörer**. Öppna en befintlig leverantör eller skapa en ny leverantör och markera sedan snabbflikarna **Diverse information**. Alla nya fält som modulen **Hemtagningskostnad** lägger till visas under rubriken **Färder**. Följande register beskriver fälten.

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
