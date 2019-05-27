---
title: Bokför transaktioner för anläggningstillgång i bokföringsskikt
description: Den här artikeln ger en översikt över bokföringsskiktsfunktionen för transaktioner för anläggningstillgångar.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22feb15a1891c57576a5809f4ff3f4d089c6dfa4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556372"
---
# <a name="post-fixed-asset-transactions-to-posting-layers"></a>Bokför transaktioner för anläggningstillgång i bokföringsskikt

[!include [banner](../includes/banner.md)]

Den här artikeln ger en översikt över bokföringsskiktsfunktionen för transaktioner för anläggningstillgångar.

En anläggningstillgång skrivs ofta av på olika sätt för olika syften. Avskrivning av skatteskäl beräknas enligt aktuella skatteregler för att uppnå högsta möjliga avskrivning före skatt, men avskrivning av rapporteringsskäl beräknas enligt redovisningslagar och -standarder. De olika typerna av avskrivning beräknas och registreras separat i bokföringsskikten.

Varje bok som är kopplad till en anläggningstillgång ställs in för ett visst bokföringsskikt som har ett allmänt avskrivningsmål. Det finns tio bokföringsskikt: Current (Aktuellt), Operations (Verksamhet), Tax (Skatt) samt sju Customs-lager (Anpassade). Du kan också avaktivera bokföring i redovisningen för boken genom att ange fältet Bokför i huvudboken som Nej. Fältet Bokföring layer ställs sedan automatiskt in på None. Böcker som inte bokför i redovisningen används som regel för momsrapporteringssyften. Denna metod ger dig dessutom flexibilitet att ta bort historiska transaktioner för tillgångsboken, detta eftersom de inte har nedtecknats i redovisningen.

Journaler för anläggningstillgångar har definierats genom att använda sidan Journal names i Huvudbok > Journalinställningar > Journalnamn. Varje journal som du kan bokföra avskrivningar i definieras av sitt journalnamn för ett bokföringsskikt. Bokföringsskiktet i journalen kan inte ändras. Denna begränsning hjälper till att säkerställa att transaktioner för respektive bokföringsskikt hålls åtskilda. Minst ett journalnamn måste skapas för varje bokföringsskikt. Om du använder böcker som inte bokför i redovisningen, måste du också skapa en journal där bokföringsskiktet är inställt på Ingen.

Du kan ange huvudbokskonton för anläggningstillgångar på sidan Bokföringsprofiler för anläggningstillgångar. För varje bokföringsprofil måste du välja relevant transaktionstyp och bok, och sedan välja huvudbokskonton. Ställ in en profilpost för bokföring för varje bok som ska bokföra i redovisningen.

> [!NOTE] 
> Genom att använda härledda böcker kan du bokföra transaktioner samtidigt till olika bokföringsskikt. Du skapar transaktionerna för den primära boken i en journal där bokföringsskiktet motsvarar bokens bokföringsskikt. I samband med bokföring bokförs transaktionerna för den härledda boken till lämpliga bokföringsskikt.

Mer information finns i [Härledda böcker](derived-books.md) och [Bokföring med härledda böcker](post-derived-value-models.md).



