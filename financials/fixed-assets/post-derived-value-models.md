---
title: "Bokför med härledda avskrivningsregler"
description: "Det här avsnittet beskriver hur du använder härledda böcker."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: ca077727910059878fb16a3f78c5b9133c6c741f
ms.lasthandoff: 03/31/2017


---

# <a name="post-with-derived-books"></a>Bokför med härledda avskrivningsregler

Det här avsnittet beskriver hur du använder härledda böcker.

När transaktioner bokförs för en bok som innehåller härledda böcker, bokförs de härledda boktransaktionerna automatiskt i journaler, inköpsorder eller fritextfakturor. Om du emellertid förbereder de primära boktransaktionerna i journalen för anläggningstillgångar kan du visa och ändra beloppen för härledda transaktioner innan de bokförs.
-   Vissa konton, som till exempel moms- och kund- eller leverantörskonton, uppdateras bara en gång genom bokföring av den primära boken. Härledda boktransaktioner bokförs på de konton som har definierats för den härledda boken på sidan för bokföringsprofiler för anläggningstillgångar.
-   Anskaffning (Acquisition) används ofta som transaktionstyp för härledda böcker. Den används när boken och härledd bok ska tillämpas för anläggningstillgången från och med dess anskaffningsdatum.
-   Även andra värden kan gälla för transaktionstypen. Om till exempel den primära boken och de härledda böckerna har samma intervaller vad gäller försäljning eller avyttring, blir alla transaktionstyper tillgängliga för inställningen av en härledd bok.

> [!WARNING]
> Den avskrivning som är bokförd i härledd bok kommer att vara densamma som det belopp som bokfördes för den primära boken. Om avskrivningsmetoderna skiljer sig åt mellan böckerna bör du inte generera avskrivningstransaktioner med den härledda processen. |

## <a name="example"></a>Exempel 
Följande information beskriver hur du skapar anskaffningstransaktioner med funktionerna för den härledda boken.

1.  Skapa böckerna på boksidan (Books).
    -   Bok för redovisning: VM 1, aktuellt bokföringsskikt
    -   Bok för skattesyften: VM 2, momsbokföringsskikt

2.  Klicka på fliken Derived books i VM 1. Välj VM 2 i fältet Books och Acquisition fältet Transaction type.

Böckerna kan sedan kopplas till specifika anläggningstillgångar. 

När en anskaffning bokförs för en anläggningstillgång med avskrivningsregel VM 1 bokförs anskaffningen inte bara på VM 1 utan även på härledd avskrivningsregel VM 2. Statusen för båda förteckning över anläggningstillgångar uppdateras till öppen.

> [!NOTE]                                                                                                         
> Om härledda böcker inte används måste du bokföra anskaffningen av anläggningstillgången för både boken VM 1 och boken VM 2.

Mer information finns i [härledda avskrivningsregler](derived-books.md)


