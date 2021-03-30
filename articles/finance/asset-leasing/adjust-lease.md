---
title: Justera leasingar
description: Ämnet förklarar hur du justerar en leasing. Justering kan krävas om leasingvillkoren ändras, leasingen utökas eller andra omständigheter ändras.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f11dbd6dc67ffccb087f67f5ce6267fe94e0ee65
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219997"
---
# <a name="adjust-leases"></a>Justera leasingar

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ämnet förklarar hur du justerar en leasing. Justering kan krävas om leasingvillkoren ändras, leasingen utökas eller andra omständigheter ändras. Leasing av tillgång följer riktlinjerna i Accounting Standards Codification Topic 842 (ASC 842) och International Financial Reporting Standard 16 (IFRS 16) om ändringar av leasing. ASC 842-20-15-1 definierar en leasingändring precis som alla ändringar av villkoren för ett kontrakt som orsakar en ändring av omfattningen av eller ersättningen av en leasing. Punkt 39 i IFRS 16 anger att en leasetagare måste omvärdera leasingskulden så att den återspeglar ändringar av leasingbetalningarna.

För organisationer som följer ASC 842 eller IFRS 16 omvärderas en leasing för att återspegla en förändring av nuvärdet för de framtida lägsta leasingbetalningarna (PVFMLP). Om PVFMLP ökar kommer journalposten som skapas att vara en debitering till kontot för tillgång med nyttjanderätt och en kredit till leasingskuldkontot för mellanskillnaden mellan nya PVFMLP och tidigare PVFMLP. Om PVFMLP minskar kommer journalposten att vara ett debetbelopp för leasingskuldkontot och en kredit till kontot för tillgång med nyttjanderätt för mellanskillnaden.

Om justeringen minskar ROU-tillgången till lägre än 0 (noll) krediteras resten till bokföringskontot för förlust vid leasingändring som har angetts på sidan **Bokföringskonton för leasing**. Systemkontona för dessa transaktioner och andra justeringsposter, till exempel klassificeringsändringar, direkta utgifter, leasingincitament, förskottsbetalningar och nedmonteringskostnader som uppstår vid leasingändringar.

Om du vill ha mer information om leasingjusteringstransaktioner rekommenderar vi att du läser i IFRS 16 och ASC 842.

## <a name="lease-adjustment-wizard"></a>Guide för leasingjustering

Gör på följande sätt om du vill justera ett leasingavtal. Den ändrade informationen uppdaterar leasingscheman efter det att du har bokfört från guiden **Leasingjustering**. Du kan spara arbetet och stänga guiden när som helst, och sedan komma tillbaka senare för att återuppta arbetet.

Öppna guiden **Leasingjustering** från leasingsammanfattningen genom att följa dessa steg.

1. Gå till **Leasing av tillgångar \> Leasing \> Sammanfattning av leasing**. 
2. Välj leasingavtalet som du vill justera och välj sedan **Justeringsguide**.
3. Följ uppmaningarna i guiden för att ange de ändringar som behövs.

Öppna guiden **Leasingjustering** från sidan **Leasingjusteringar** genom att följa stegen nedan och göra en justering som redan pågår.

1.  Gå till **Leasing \> Leasingavtal \> Leasingjusteringar**.
2.  Välj ett leasingavtal som har justeringsstatusen **Pågår** och välj sedan **Justeringsguide**.
3.  I fälten **Startdatum för ändring** och **Bokföringsdatum** anger du tillhörande datum.
4.  Välj **Nästa**.

    Leasingavtalet läggs nu till på sidan **Leasingjusteringar**, där du kan ange ny information om det.

    När leasingavtalet har justerats gäller följande beaktandefält för nyttjanderätt. Om inga direkta utgifter, leasingincitament, förskottsbetalningar eller nedmonteringskostnader är associerade med den ändrade leasingen ska du lämna tillhörande fält tomma. De ursprungliga beloppen gäller inte för den uppdaterade leasingen. 

    En leasegivare ger till exempel ett 1 000 USD incitament för att godkänna ett leasingtillägg. I detta fall anger du **1 000** i fältet **Leasingincitament som uppstår genom justering** när du justerar leasingen så att denna beaktar tillägget.

    Betalplanraderna visar nu alla betalningar från månaden, och senare månaderna, i fältet **Startdatum för ändring**. Eftersom ändringar är framtida kan betalplanrader inte starta innan ändringen startar. Om du vill visa betalplanrader från före startdatumet för ändringen går du till sidan **Leasingversionshistorik**.

8.  Välj **Nästa**.

    På nästa sida visas nyckeluppgifter om den förväntade leasingjusteringen, till exempel redovisade värden för leasingskulden före ändringen och den nya förväntade leasingskulden efter ändringen. På sidan visas också en förhandsgranskning av journalposten för den förväntade leasingjusteringen.

9.  Välj **Skicka till arbetsflödet** för att skicka leasingjusteringen till arbetsflödessystemet om arbetsflödet för leasingjustering är aktivt och justeringen ännu inte har godkänts. Mer information om hur du använder arbetsflödet för leasingjustering finns i [Använda arbetsflöden för leasingjustering](use-create-lease-wrkflw.md).

    > [!NOTE]
    > Nu räknar systemet om justeringsvariablerna för att kontrollera att inga transaktioner har bokförts mot leasingavtalet sedan justeringsöversikten och justeringsjournalposten först beräknades. Om några värden ändras uppdateras rutnätet för justeringsöversikten, och du kan granska informationen innan du skickar leasingjusteringarna till arbetsflödessystemet på nytt.

10. Om ett arbetsflöde inte är aktivt, eller om leasingjusteringen har godkänts, väljer du **Slutför** för att bearbeta ändringarna och bokföra justeringsjournalposten.

    > [!NOTE] 
    > Nu räknar systemet om justeringsvariablerna för att kontrollera att inga transaktioner har bokförts mot leasingavtalet sedan justeringsöversikten och justeringsjournalposten först beräknades. Om värdena ändras uppdateras justeringsöversiktens rutnät och du kan granska ändringarna innan du väljer **Slutför**. Om arbetsflödet är aktivt och leasingjusteringen har godkänts, medför ändringar i justeringsöversikten att godkännandestatusen får statusvärdet **Ej skickad**. I det här fallet ska du skicka om leasingjusteringen till arbetsflödessystemet.

    På sidan **Leasingjusteringar** är justeringsstatusen nu inställd på **Slutfört**.

    På sidan **Leasingjusteringar** kan du fortfarande visa snabbflikarna **Justeringsöversikt** och **Förhandsversion av justeringspost**. Leasingdetaljer och datuminformation visas i versionshistoriken för leasingavtalet.

    En ny leasingversion och en ny uppsättning tidsplaner skapas nu med den ändrade informationen. 

13. Om du vill visa nya tidsplaner går du till leasingavtalet och väljer **Böcker**.
14. Välj **Betalplan** och du vill visa det nyskapade betalplant.
15. Om du vill visa den nya amorteringsplanen för leasingskulder som har genererats från den nya informationen, stänger du sidan **Betalningsplan** och öppnar sidan **Plan för amortering av skuld**.
16. Om du vill visa den nya avskrivningsplanen för tillgångar öppnar du sidan **Avskrivningsplan för tillgång** från sidan **Information om bok**.
17. För att visa den justerade journalposten väljer du **Journaler \> Journal för leasing av tillgång**.

## <a name="cancel-a-lease-adjustment"></a>Avbryta en leasingjustering

Ta bort en leasingjustering som pågår genom att följa dessa steg.

1.  Gå till **Leasing \> Leasingavtal \> Leasingjusteringar**.
2.  Markera den pågående justering av leasingavtalet som ska annulleras.
3.  Välj **Avbryt justering**. 
4.  Välj **OK**.

    > [!NOTE] 
    > Om du väljer **Avbryt** i guiden **Leasingjustering** återställer du den senaste ändringen som du har slutfört i guiden, men tar inte bort en justering som pågår.

## <a name="use-the-lease-adjustment-workflow"></a>Använda arbetsflödet för leasingjustering

I det här avsnittet beskrivs hur du använder arbetsflödet för leasingjustering. Arbetsflödet för leasingjustering gör det lättare att hantera leasingjusteringar på ett konsekvent sätt genom att tillhandahålla en uppsättning godkännandesteg och tilldela dem till specifika användare som godkänner en leasingjustering innan den godkänns. När leasingjusteringen har godkänts i arbetsflödet kan du använda guiden **Leasingjustering** för att slutföra leasingjusteringen.

1.  Om du vill skicka in en leasingjustering för godkännande går du till **Leasing \> Leasings \> Leasingjusteringar**.
2.  Välj leasing-ID för leasingjusteringen och välj sedan **Justeringsguide**.
3.  På sista sidan i guiden väljer du **Skicka för godkännande**.
4.  Ange en kommentar om justeringen och välj sedan **OK**.

    Arbetsflödets status ändras till **Väntar på godkännande** och alla fält i guiden är låsta för redigering.

5.  Om du vill godkänna leasingjusteringen går du till **Leasing \> Leasings \> Leasingjusteringar**.
6.  Välj leasing-ID för leasingjusteringen och granska snabbflikarna **Justeringsöversikt** och **Förhandsversion av justeringspost**.
7.  Välj **Arbetsflöde \> Godkänt**.

    På sidan **Leasingjusteringar** är arbetsflödessstatusen nu inställd på **Godkänd**. Vid denna tidpunkt är leasingjusteringen klar att bokföras genom justeringsjournalposten.

8.  Gå till **Leasing \> Leasings \> Leasingjusteringar** om du vill fortsätta bearbeta leasingjusteringen och bokföra justeringsposten.
9.  Välj leasing-ID för leasingjusteringen och välj sedan **Justeringsguide**.
10. Välj **Nästa** tills du kommer till sista sidan i guiden och välj sedan **Slutför**.

Systemet räknar om de bokförda värdena i leasingavtalet för att säkerställa att justeringsvariablerna som godkändes är aktuella. Om det finns ändringar ändras godkännandestatusen till **Utkast**, och du bör skicka in leasingjusteringen till arbetsflödessystemet på nytt.

## <a name="view-lease-versions"></a>Visa leasingversioner

Om en leasing har justerats kan du visa olika versioner av den. Du kan också visa historiska planer och tidigare leasinguppgifter.

1. På sidan **Sammanfattning av leasing** väljer du leasingen och i åtgärdsfönstret väljer du sedan **Versionshistorik för leasing**.

    Om den valda leasingen har justerats visar sidan **Versionshistorik för leasing** de olika versionerna. Den ursprungliga leasingen är märkt **1** och efterföljande versioner har stigande numerisk ordning.

    För en vald leasingversion kan du visa de ekonomiska dimensionerna, kontraktsinformation, plats och betalningsplansrader.

2. Om du vill visa historiska planer öppnar du den ändrade leasingen från sidan **Sammanfattning av leasing**, väljer önskad bok och väljer sedan **Versionshistorik för bok** i åtgärdsfönstret.
3. På sidan **Bokversion** väljer du en version och plan att visa.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]