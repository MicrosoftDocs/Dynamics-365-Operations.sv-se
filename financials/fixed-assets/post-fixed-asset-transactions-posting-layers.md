---
title: "Bokföra transaktioner för anläggningstillgång i bokföringsskikt"
description: "Den här artikeln ger en översikt över bokföringsskiktsfunktionen för transaktioner för anläggningstillgångar."
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
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 4b112eee303604149c7609972a60c2014d4be423
ms.lasthandoff: 03/31/2017


---

# <a name="post-fixed-asset-transactions-to-posting-layers"></a>Bokföra transaktioner för anläggningstillgång i bokföringsskikt

Den här artikeln ger en översikt över bokföringsskiktsfunktionen för transaktioner för anläggningstillgångar.

En anläggningstillgång skrivs ofta av på olika sätt för olika syften. Avskrivning av skatteskäl beräknas enligt aktuella skatteregler för att uppnå högsta möjliga avskrivning före skatt, men avskrivning av rapporteringsskäl beräknas enligt redovisningslagar och -standarder. De olika typerna av avskrivning beräknas och registreras separat i bokföringsskikten.

Varje bok som är kopplad till en anläggningstillgång ställs in för ett visst bokföringsskikt som har ett allmänt avskrivningsmål. Det finns tio bokföringsskikt: Current (Aktuellt), Operations (Verksamhet), Tax (Skatt) samt sju Customs-lager (Anpassade). Du kan också avaktivera bokföring i redovisningen för boken genom att ange fältet Post to general ledger som No. Fältet Posting layer ställs sedan automatiskt in på None. Förteckningar som inte bokföra i redovisningen används normalt för momsrapportering. Denna metod ger ytterligare flexibilitet att ta bort historiska transaktioner, för tillgångsförteckningen, eftersom de inte har bekräftats i redovisningen.

Journaler för anläggningstillgångar har definierats genom att använda sidan Journal names i General ledger > Journal setup > Journal names. Varje journal som du kan bokföra avskrivningar i definieras av sitt journalnamn för ett bokföringsskikt. Bokföringsskiktet i journalen kan inte ändras. Denna begränsning hjälper till att säkerställa att transaktioner för respektive bokföringsskikt hålls åtskilda. Minst ett journalnamn måste skapas för varje bokföringsskikt. Om du använder avskrivningsregler som inte bokföra i redovisningen, måste du också skapa en journal där bokföringsskikt är inställd på Ingen.

Du kan ange huvudbokskonton för anläggningstillgångar på sidan Fixed asset posting profiles. För varje bokföringsprofil måste du välja relevant transaktionstyp och bok, och sedan välja huvudbokskonton. Ställ in en profilpost för bokföring för varje bok som ska bokföra i redovisningen.

> [!NOTE] 
> Med härledda avskrivningsregler kan bokföra du transaktioner till olika bokföringsskikt samtidigt. Du skapar transaktionerna för den primära boken i en journal där bokföringsskiktet motsvarar bokens bokföringsskikt. I samband med bokföring bokförs transaktionerna för den härledda boken till lämpliga bokföringsskikt.

Mer information finns i [härledda avskrivningsregler](derived-books.md) och [bokföring med härledda avskrivningsregler](post-derived-value-models.md).


