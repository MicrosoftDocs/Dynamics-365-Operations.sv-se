---
title: Skaffa tillgångar genom anskaffning
description: Det här ämnet beskriver hur du ställer in integrationen mellan Anläggningstillgångar och Leverantörsreskontra om du automatiskt vill skapa anläggningstillgångar från inköpsorder eller leverantörsfakturor, eller automatiskt bokföra anskaffningar och anskaffningsjusteringar för anläggningstillgångar.
author: ShylaThompson
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 3481
ms.assetid: d4e73a3f-633b-48b2-b8db-7a4a59a4d7ec
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6dcf5088e0c2d61b453f374c73b66843f74e98d1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827060"
---
# <a name="acquire-assets-through-procurement"></a>Skaffa tillgångar genom anskaffning

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver hur du ställer in integrationen mellan Anläggningstillgångar och Leverantörsreskontra om du automatiskt vill skapa anläggningstillgångar från inköpsorder eller leverantörsfakturor, eller automatiskt bokföra anskaffningar och anskaffningsjusteringar för anläggningstillgångar. En inköpsrad skapar en tillgång oavsett kvantiteten på inköpsraden. Om du behöver skapa flera anläggningstillgångar måste du skapa flera inköpsrader.

 Följande metoder används för integration av anläggningstillgångar och leverantörsreskontra och du måste använda samma metod för alla anläggningstillgångar:
-   Du skapar en anläggningstillgång manuellt innan du lägger till anläggningstillgångens nummer på raden i inköpsordern eller leverantörsfakturan. En anskaffningstransaktion bokförs automatiskt för tillgången när du bokför leverantörsfakturan. Det här är standardmetoden.
-   Du skapar en anläggningstillgång manuellt innan du lägger till anläggningstillgångens nummer på raden i inköpsordern eller leverantörsfakturan. Ingen anskaffningstransaktion bokförs för tillgången när du bokför leverantörsfakturan.
-   En ny anläggningstillgång skapas automatiskt när du bokför en produktinleverans eller leverantörsfakturan där kryssrutan Skapa en ny anläggningstillgång är markerad. En anskaffningstransaktion bokförs automatiskt för tillgången när du bokför leverantörsfakturan.
-   En ny anläggningstillgång skapas automatiskt när du bokför en produktinleverans eller leverantörsfakturan där kryssrutan Skapa en ny anläggningstillgång är markerad. Ingen anskaffningstransaktion bokförs för tillgången när du bokför leverantörsfakturan.

Välj någon av de två första metoderna om du föredrar att skapa anläggningstillgångar manuellt, och sedan tilldela Anläggningstillgångsnumret till inköpsordern eller leverantörsfakturan. Välj någon av de två sista metoderna om du föredrar ett mer flexibelt sätt: ibland kanske du vill skapa anläggningstillgångar manuellt, och ibland automatiskt skapa en ny anläggningstillgång som baseras på Anläggningstillgångsinformationen i radartikeldetaljerna. 

Oavsett om du skapar anläggningstillgångar manuellt eller använder det flexibla sättet, gäller det andra beslutet huruvida en anskaffningstransaktion bara kan bokföras i Anläggningstillgångar, eller om den kan bokföras när du bokför en leverantörsfaktura. Vissa organisationer föredrar att användarna manuellt skapar anskaffningar och anskaffningstransaktioner i Anläggningstillgångar genom manuell journalregistrering eller genom förslag. 

I det här avsnittet beskrivs respektive metod mer ingående.

## <a name="methods-for-manually-creating-fixed-assets"></a> Metoder för att manuellt skapa anläggningstillgångar
När du bokför en faktura som har ett Anläggningstillgångsnummer registrerat på raderna, och sidan Tillåt förvärv av tillgångar från inköp på sidan Parametrar för anläggningstillgångar bokförs förvärvet automatiskt och tillgångens status ändras till Öppen. 

Om ett förvärv inte kan bokföras kan du antingen registrera en anskaffningstransaktion manuellt i Anläggningstillgångar, eller använda ett anskaffningsförslag i Journal för anläggningstillgångar för att skapa flera anskaffningstransaktioner samtidigt.

> [!NOTE]                                                                                                                              
> Om Anläggningstillgångar har ställts in att begränsa bokföring av anskaffningstransaktioner till en viss användargrupp, måste en medlem i den gruppen bokföra anskaffningstransaktioner från fakturor.

## <a name="methods-for-automatically-creating-fixed-assets"></a> Metoder för att automatiskt skapa anläggningstillgångar
När du bokför en produktinleverans som har alternativet Skapa en ny anläggningstillgång markerat för en rad skapas en ny anläggningstillgång som har statusen Ännu inte anskaffad. När du sedan bokför en leverantörsfaktura med en ny anläggningstillgång, bokförs en anskaffningstransaktion för den nya tillgången och tillgångens status ändras till Öppen, om Anlläggningstillgångar har ställts in för att tillåta tillgångsanskaffning från Leverantörsreskontra och du är medlem i en grupp som kan bokföra anskaffningstransaktioner. 

Om kryssrutan Ny anläggningstillgång inte markeras på inköpsraden när du bokför produktinleveransen, men markerades när du bokförde leverantörsfakturan, skapas den nya anläggningstillgången och förvärvas med statusen Öppen, om Anläggningstillgången har ställts in så att det går att skapa och förvärva. Ingen mer tillgång skapas när du bokför en leverantörsfaktura som skapades redan när du bokförde produktinleveransen.

### <a name="capitalization-threshold"></a>Kapitaliseringströskel

När du använder en metod där en tillgång skapas och förvärvas automatiskt, kan du ställa in systemet till att verifiera om inköpsbeloppet för anläggningstillgången uppfyller en angiven kapitaliseringströskel för tillgångens avskrivning. Om så är fallet markeras alternativet Depreciation (avskrivning) i böckerna för den tillgång när denna skapas från Accounts payable (leverantörsreskontra). 

En kapitaliseringströskel är ett valutabelopp som bestämmer om tillgångar ska skrivas av om de uppfyller det angivna beloppet. Om du till exempel köper en tillgång och inköpsbeloppet är mindre än kapitaliseringströskeln, skrivs tillgången inte av. Om inköpsbeloppet är lika med eller större än kapitaliseringströskeln skrivs tillgången av. 

Du ställer in kapitaliseringströskeln på sidan Anläggningstillgångsgrupper.

## <a name="scenario"></a>Scenario
I följande scenario beskrivs en fullständig cykel där Anläggningstillgångar integreras med Leverantörsreskontra. Här beskrivs exempelinställningar samt även hur du använder anskaffningsförslag. 

I det här scenariot används följande inställningar:

-   Tillgångar skapas automatiskt när produktinleveransen eller leverantörsfakturan bokförs, men Anläggningstillgångar är inställt på att förhindra bokföring av anskaffningstransaktioner från Leverantörsreskontra.
-   Konton anges i fältet Kontotyp för kontotyperna Inleverans av anläggningstillgångar och Utleverans av anläggningstillgångar på sidan Artikelgrupper.
-   Kapitaliseringströskel för gruppen Datorer (COMP) är 15 000.
-   Din uppgift är att registrera en inköpsorder för en ny bärbar dator som en medarbetare ska använda, bokföra inköpsordern, verifiera att den leveransansvariga bokför en produktinleverans och sedan bokför fakturan och verifiera att revisorn uppdaterar tillgången till statusvärdet Öppen.

Till att börja med ska du använda sidan Inköpsorder för att registrera uppgifter om den bärbara datorn, som kostar 16 000 kronor. Markera alternativet Ny anläggningstillgång? på snabbfliken Anläggningstillgångar på inköpsorderraden, välj COMP som Anläggningstillgångsgrupp och spara inköpsordern. 

När den bärbara datorn inlevereras, registrerar och bokför den leveransansvarige en produktinleverans vilket registrerar inleveransen av den bärbara datorn. Tillgången bärbar dator skapas och har statusen Ännu inte anskaffad. Beloppet överskrider kapitaliseringströskeln. Därför väljs alternativet Deprecation (Avskrivning) i böckerna för tillgången bärbar dator. Följande transaktioner görs.

| Beskrivning                               | Konto             | Debet    | Kredit   |
|-------------------------------------------|---------------------|----------|----------|
| Inköp, produktinleverans för inköp        | Ofakturerade inleveranser | 16 000,00 |          |
| Inköp, produktinleverans, inköpsmotkonto | Periodiserade inköp   |          | 16 000,00 |

Sedan bokför du leverantörsfakturan för datorn. Statusen Bärbar dator ändras inte, eftersom Anläggningstillgångar ställs in för att förhindra att en Anläggningstillgångstransaktion bokförs, när en leverantörsfaktura bokförs. Alternativet Skapa en ny anläggningstillgång markerades när leverantörsfakturan bokfördes. Därför användes kontot Inleverans av anläggningstillgång. Kontot Utleverans av anläggningstillgång för anläggningstillgången användes inte, eftersom inget förvärv bokfördes; det kommer att användas senare när organisationens revisor bokför en anskaffningstransaktion i Anläggningstillgångar med förvärvsförslag. 

Följande transaktioner görs.

| Beskrivning                               | Konto             | Debet    | Kredit   |
|-------------------------------------------|---------------------|----------|----------|
| Inköp, produktinleverans, inköpsmotkonto | Periodiserade inköp   | 16 000,00 |          |
| Leverantörssaldo                            | Leverantörsreskontra    |          | 16 000,00 |
| Inköp, Inleverans av anläggningstillgång             | Datorutgift    | 16 000,00 |          |
| Inköp, produktinleverans för inköp        | Ofakturerade inleveranser |          | 16 000,00 |

Slutligen går revisorn igenom alla anläggningstillgångar som har statusen Ännu inte anskaffad. Därför måste den nya tillgången bärbar dator granskas. Revisorn öppnar sedan sidan Anskaffningsförslag från journalraderna i Anläggningstillgångar och skapar anskaffningstransaktioner för alla tillgångar som har en faktura men som fortfarande har statusvärdet Ännu inte anskaffad. När journalen bokförs, ändras statusen för tillgången bärbar dator till Öppen. Kontot Utleverans av anläggningstillgång krediteras och kontot Tillgångsförvärv debiteras. 

Följande varianter finns för scenariot:

-   Om Anläggningstillgångar har ställts in så att anskaffningstransaktioner för tillgångar kan bokföras när leverantörsfakturor bokförs, behöver revisorn inte använda anskaffningsförslag i Anläggningstillgångar eftersom anskaffningstransaktionen skapas. Olika konton uppdateras också när du bokför leverantörsfakturan. I stället för Datorutgift debiteras lagerkontot för Inleverans av anläggningstillgång och två ytterligare transaktioner görs: kontot Tillgångsförvärv debiteras och Lagerkontot för Utleverans av anläggningstillgång krediteras.
-   Om alternativet Skapa en ny anläggningstillgång inte markeras när produktinleveransen bokförs, skapas ingen tillgång vid den tidpunkten. Om du markerar alternativet Skapa en ny anläggningstillgång innan du bokför leverantörsfakturan, skapas tillgången med Ännu inte anskaffad eller med statusvärdet Öppen om du även bokför anskaffningstransaktioner när leverantörsfakturor bokförs.
-   Om kostnaden för den bärbara datorn är 14 000 kronor istället för 16 000 kronor, uppnås inte kapitaliseringströskeln. Därför skapas tillgången och alternativet Avskrivning avmarkeras.
-   Om ett fakturaregister används, använder du sidan Fakturagodkännandejournal efter att fakturaregistret har bokförts för att inleverera verifikationen, länka inköpsordern till leverantörsfakturan, markera alternativet Skapa en ny anläggningstillgång och bokför sedan fakturan. Om du tillhör en användargrupp som kan skapa anskaffningstransaktioner skapas anskaffningen och tillgången får statusvärdet Öppen.
-   Om enbart en delkvantitet inlevereras, skapas ingen tillgångsanskaffning för den första leverantörsfakturan på grund av användargruppsrestriktioner. Det enda sättet som en anskaffning kan bokföras på för den andra leverantörsfakturan som avslutar den beställda kvantiteten, är om en anskaffningstransaktion redan har registrerats för den första leverantörsfakturan, och du tillhör en användargrupp som tillåts bokföra anskaffningar.


Mer information finns i [Integrering av anläggningstillgångar](fixed-asset-integration.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]