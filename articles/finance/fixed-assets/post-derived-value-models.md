---
title: Bokför med härledda böcker
description: Det här avsnittet beskriver hur du använder härledda böcker.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: kfend
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0270ad1e66193832fb1139fca4439b36b5ffb84
ms.sourcegitcommit: dca54dd3afc7c94795d89c63050b105df2c48e3f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2022
ms.locfileid: "9682918"
---
# <a name="post-with-derived-books"></a>Bokför med härledda böcker

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du använder härledda böcker.

När transaktioner bokförs för en bok som innehåller härledda böcker, bokförs de härledda boktransaktionerna automatiskt i journaler, inköpsorder eller fritextfakturor. Om du emellertid förbereder de primära boktransaktionerna i journalen för anläggningstillgångar kan du visa och ändra beloppen för härledda transaktioner innan de bokförs.
-   Vissa konton, som till exempel moms- och kund- eller leverantörskonton, uppdateras bara en gång genom bokföring av den primära boken. Härledda boktransaktioner bokförs på de konton som har definierats för den härledda boken på sidan för bokföringsprofiler för anläggningstillgångar.
-   Anskaffning (Acquisition) används ofta som transaktionstyp för härledda böcker. Den används när boken och härledd bok ska tillämpas för anläggningstillgången från och med dess anskaffningsdatum.
-   Även andra värden kan gälla för transaktionstypen. Om till exempel den primära boken och de härledda böckerna har samma intervaller vad gäller försäljning eller avyttring, blir alla transaktionstyper tillgängliga för inställningen av en härledd bok.

> [!WARNING]
> Den avskrivning som är bokförd i härledd bok kommer att vara densamma som det belopp som bokfördes för den primära boken. Om avskrivningsmetoderna skiljer sig åt mellan böckerna bör du inte generera avskrivningstransaktioner med den härledda processen. 

## <a name="example"></a>Exempel 
Följande information beskriver hur du skapar anskaffningstransaktioner med funktionerna för den härledda boken.

1.  Skapa böckerna på boksidan (Böcker).
    -   Bok för redovisning: VM 1, aktuellt bokföringsskikt
    -   Bok för skattesyften: VM 2, momsbokföringsskikt

2.  Klicka på fliken Härledda böcker i VM 1. Välj VM 2 i fältet Bok samt Tillgång i fältet Transaktionstyp.

Böckerna kan sedan kopplas till specifika anläggningstillgångar. 

När en anskaffning bokförs för en anläggningstillgång med bok VM 1 bokförs anskaffningen inte bara på VM 1 utan även på den härledda boken VM 2. Statusen för båda böckerna för anläggningstillgång uppdateras till Öppen.

> [!NOTE]                                                                                                         
> Om härledda böcker inte används måste du bokföra anskaffningen av anläggningstillgången för både boken VM 1 och boken VM 2.

Mer information finns i [Härledda böcker](derived-books.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
