---
title: Bokför transaktioner för anläggningstillgång i bokföringsskikt
description: Den här artikeln ger en översikt över bokföringsskiktsfunktionen för transaktioner för anläggningstillgångar.
author: moaamer
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf35194badfa3c09758ad4dd9927af172a4ffdab
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990550"
---
# <a name="post-fixed-asset-transactions-to-posting-layers"></a>Bokför transaktioner för anläggningstillgång i bokföringsskikt

[!include [banner](../includes/banner.md)]

Den här artikeln ger en översikt över bokföringsskiktsfunktionen för transaktioner för anläggningstillgångar.

En anläggningstillgång skrivs ofta av på olika sätt för olika syften. Avskrivning av skatteskäl beräknas enligt aktuella skatteregler för att uppnå högsta möjliga avskrivning före skatt, men avskrivning av rapporteringsskäl beräknas enligt redovisningslagar och -standarder. De olika typerna av avskrivning beräknas och registreras separat i bokföringsskikten.

Varje bok som är kopplad till en anläggningstillgång ställs in för ett visst bokföringsskikt som har ett allmänt avskrivningsmål. Det finns tio bokföringsskikt: Current (Aktuellt), Operations (Verksamhet), Tax (Skatt) samt sju Customs-lager (Anpassade). Du kan också avaktivera bokföring i redovisningen för boken genom att ange fältet Bokför i huvudboken som Nej. Fältet Bokföring layer ställs sedan automatiskt in på None. Böcker som inte bokför i redovisningen används som regel för momsrapporteringssyften. Denna metod ger dig dessutom flexibilitet att ta bort historiska transaktioner för tillgångsboken, detta eftersom de inte har nedtecknats i redovisningen.

Journaler för anläggningstillgångar har definierats genom att använda sidan Journal names i Huvudbok > Journalinställningar > Journalnamn. Varje journal som du kan bokföra avskrivningar i definieras av sitt journalnamn för ett bokföringsskikt. Bokföringsskiktet i journalen kan inte ändras. Denna begränsning hjälper till att säkerställa att transaktioner för respektive bokföringsskikt hålls åtskilda. Minst ett journalnamn måste skapas för varje bokföringsskikt. Om du använder böcker som inte bokför i redovisningen, måste du också skapa en journal där bokföringsskiktet är inställt på Ingen.

Du kan ange huvudbokskonton för anläggningstillgångar på sidan Bokföringsprofiler för anläggningstillgångar. För varje bokföringsprofil måste du välja relevant transaktionstyp och bok, och sedan välja huvudbokskonton. Ställ in en profilpost för bokföring för varje bok som ska bokföra i redovisningen.

Anläggningstillgången kan anges i dokument som bara stöder det **aktuella** bokföringsskiktet, som **Inköpsorder**, **Pågående leverantörsfaktura**, **Försäljningsorder** och **Fritextfaktura**. När du väljer ett anläggningstillgångs-ID i något av dessa dokument, filtreras till tillgångsboken med **aktuellt** bokföringsskikt och fylls i automatiskt vid bokföring när systemet validerar att bokföringsskiktet för anläggningstillgången är **Aktuellt**. Om valideringen inte kan slutföras avbryts bokföringsprocessen. 

> [!NOTE] 
> Genom att använda härledda böcker kan du bokföra transaktioner samtidigt till olika bokföringsskikt. Transaktionerna för den primära boken skapas i en journal eller ett källdokument där bokföringsskiktet motsvarar bokens bokföringsskikt. I samband med bokföring bokförs transaktionerna för den härledda boken till lämpliga bokföringsskikt. 


Mer information finns i [Härledda böcker](derived-books.md) och [Bokföra med härledda böcker](post-derived-value-models.md).



