---
title: Lagerstängning
description: Som en del av processen för att kvitta utleveranstransaktioner med inleveranstransaktioner, kan du också välja att uppdatera redovisningen med justeringarna som har gjorts.
author: AndersGirke
manager: tfehr
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.custom: 61973
ms.assetid: c210c882-6849-4704-b78c-a777dd6cfdb6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1169ad784c07d0757990b36b618282ed7858bcbf
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987564"
---
# <a name="inventory-close"></a>Lagerstängning

[!include [banner](../includes/banner.md)]

Som en del av processen för att kvitta utleveranstransaktioner med inleveranstransaktioner, kan du också välja att uppdatera redovisningen med justeringarna som har gjorts.

Lagerstängningsprocessen kvittar utleveranstransaktioner mot inleveranstransaktioner baserat på den lagervärderingsmetod som har valts i artikelns artikelmodellgrupp. Som en del av kvittningsprocessen kan du ange att redovisningen ska uppdateras, så att den återspeglar justeringarna som har gjorts. Till dess att lagerstängningen eller omberäkningen utförs bokför emellertid utleveranstransaktioner till den beräknade löpande genomsnittliga självkostnaden. 

Efter lagerstängningen går det inte längre att bokföra i perioder före det inställda lagerstängningsdatumet, såvida du inte återför en genomförd lagerstängning. Om lagerstängningen exempelvis körs för perioden som slutar den 31 januari, kan du inte bokföra transaktioner som har ett datum som infaller före den 31 januari. 

Artiklar i lagret tilldelas en av två lagertyper: artikel eller tjänst Lagerstängningen utför samma funktioner för båda typerna. För serviceartiklar kvittar lagerstängningen fortfarande utleveranser mot inleveranser. 

Hur ofta lagerstängningsprocessen körs varierar mellan olika företag. Transaktionsvolymen bör hjälpa dig att bestämma hur ofta du väljer att köra en lagerstängning. I allmänhet kör de flesta företag en lagerstängning vid månadsstängning och avstämning.

## <a name="inventory-recalculation-and-the-general-ledger"></a>Lageromberäkning och redovisning
Om du behöver justeringarna av lagret och redovisningen under månadens gång eller någon annan lagerperiod, kan du köra en lageromberäkning i stället för en lagerstängning. Lageromberäkningen utför justeringar, men gör inga kvittningar av lagertransaktioner. 

Under lageromberäkning justeras lagerbehållning och lagertransaktioner och lageromberäkningar och lagerstängningar körs. De här uppgifterna påverkar alla huvudbokskonton som är länkade till den ursprungliga lagertransaktionen. 

**Exempel** 

När du skapar en försäljningsorder från en inköpsorder uppdateras de redovisningskonton som används för den ursprungliga försäljningsordern. Även om redovisningskontona för den artikelgrupp som är tilldelad till den här artikeln har ändrats sedan försäljningsordern bokfördes och en lageromberäkning skapat ett justeringsbelopp kommer justeringsbeloppet ändå att bokföras till de ursprungliga redovisningskontona. Det justerade beloppet ska inte bokföras till de nya redovisningskontona som tilldelas artikeln. 

När uppdateringen har slutförts kan du granska den redovisningsverifikation som bokförts som ett resultat av de här uppgifterna.

1.  Välj den uppdatering som ska granskas på sidan **Stängning och justering** på fliken **Översikt**.
2.  Klicka på **Detaljer** och välj sedan **Verifikation**.

## <a name="effects-of-the-inventory-close-process-on-the-general-ledger"></a>Effekter av lagerstängningsprocessen i redovisningen
Flera av de uppgifter du kan utföra från sidan **Stängning och justering** medför en uppdatering i redovisningen. Till exempel, redovisningen uppdateras när du gör justeringar av lagerbehållning, justeringar av lagertransaktioner, omberäkningar av lager samt lagerstängningar. 

De redovisningskonton som uppdateras till följd av det här arbetet är länkade till den ursprungliga lagertransaktionen. Om till exempel en försäljningsorder kvittas mot en inköpsorder, justeras de redovisningskonton som används för den ursprungliga försäljningsordern. Detta gäller även om redovisningskontona för den artikelgrupp som har tilldelats artikeln har ändrats sedan försäljningsordern bokfördes. När ett kvittningsbelopp skapas vid lagerstängning bokförs kvittningsbeloppet fortfarande till de ursprungliga huvudbokskontona – inte till de nya huvudbokskontona som tilldelats till artikeln. Redovisningen kan också uppdateras genom att återföra en lagerstängning. 

> [!NOTE] 
> - Lagerstängning är ett obligatoriskt steg i proceduren för stängning av månad för alla lagermodeller förutom rörligt genomsnitt.  Du kommer att varnas om du försöker stänga en räkenskapsperiod utan att först utföra lagerstängningen som av periodens slutdatum.
> - Innan du kör stängningsproceduren kan du visa en lista med artiklar som inte kan kvittas under uppdateringen.
> - Vi rekommenderar att du kör lagerstängningen utanför arbetstid så att datorresurserna belastas mer jämnt.

## <a name="the-inventory-close-log"></a> Lagerstängningsloggen
När lagerstängningen har slutförts visas ett meddelande i meddelandecenter med information om att kostnadspriset för en enhet kan vara fel eftersom en transaktion inte kunde kvittas fullt ut. 

Innan detta meddelande visas rapporterar systemet artikelnummer och berörd transaktion. Meddelandet informerar dig om att kostnadsbeloppet som används för den här transaktionen inte uppdaterats till följd av lagerstängningen. Meddelandet visas när en transaktion av utleveranstyp inte kan kvittas. 

Vid en lagerstängningsprocess kontrollerar systemet varje ekonomisk dimension för att undersöka om det finns fler utleveranser än inleveranser fram till det angivna stängningsdatumet. Denna typ av obalans kan uppstå när en inventeringstransaktion från en inköpsorder inte är helt ekonomiskt bokförd eftersom leverantörsfakturan inte har inlevererats, eller på grund av att strukturlistekomponenter som ingår i en produktion på en högre nivå är inte ekonomiskt bokförda. (Delproduktionen kostnadsberäknas inte). I detta fall kommer den påföljande stängningen inte att justera alla utleveranser till korrekt självkostnadspris, detta eftersom det inte finns tillräckligt med inleveransinformation. 

För varje stängningskörning kommer systemet att ange om en logg som innehåller varningarna lagras och kan visas. 

Om du får flera varningar i meddelandet rekommenderar vi att du vidtar följande åtgärder:

-   Uppdatera inleveranser ekonomiskt.
-   Fortsätt till UB-datumet.
-   Utvärdera dina affärsprocesser.

Det kan förekomma omständigheter där du kan inte göra något åt varningarna. När till exempel markering används, och den markerade inköpsordern har ett ekonomiskt datum efter stängningsdatumet, kan inte stängningsdatumet ändras.

## <a name="reversing-a-completed-inventory-close"></a>Återföra en genomförd lagerstängning
I vissa fall kanske du måste återföra en genomförd lagerstängning för att återställa kvittningarna till det läge de hade innan justeringarna gjordes. När du återför en genomförd lagerstängning, öppnas lagret igen så att du kan bokföra i perioden som lagerstängningen omfattar. Relaterade ändringar kan även behöva göras i redovisningen. När du är klar med att göra justeringar kan du köra lagerstängningen igen för den period som du arbetar med. 

> [!NOTE] 
> Endast den senaste lagerperioden som har stängts kan öppnas igen. För att återföra en tidigare lagerstängning måste du återföra alla efterföljande lagerstängningar en i taget och börja med de senaste.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]