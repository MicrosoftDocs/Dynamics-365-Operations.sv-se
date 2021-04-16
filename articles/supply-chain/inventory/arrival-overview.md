---
title: Införselöversikt
description: Det här avsnittet ger information om funktionen Införselöversikt. Sidan för införselöversikt är en del av den här funktionen och ger en översikt över alla artiklar som förväntas ankomma som inkommande artiklar.
author: perlynne
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverview, WMSArrivalOverviewProfile, WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 734fbdd6f62c192580029a24844fff78fda8b919
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809600"
---
# <a name="arrival-overview"></a>Införselöversikt

[!include [banner](../includes/banner.md)]

Det här avsnittet ger information om funktionen Införselöversikt. Sidan för införselöversikt är en del av den här funktionen och ger en översikt över alla artiklar som förväntas ankomma som inkommande artiklar.

Sidan **Införselöversikt** sidan ger en överblick över alla förväntade inkommande artiklar. Den visar också införsel som kan initieras utifrån översikten. Det här avsnittet fokuserar på inleveransprocessen.

## <a name="business-scenario"></a>Affärsscenario
Föreställ dig följande scenario i inkommande processer.

[![Affärsscenario](./media/arrival-overview-scenario.png)](./media/arrival-overview-scenario.png)

Sammy, inleveransansvarig, vill veta vad som förväntas inlevereras den aktuella dagen. På sidan **Införselöversikt** kan Sammy få en översikt över pågående aktiviteter och en grov uppskattning av kvantiteter, volym, vikt, olika ordertyper och så vidare. Senare ankommer en leverans på en av inlastningsplatserna och Sammy tar emot en lista med leveransen. På sidan **Införselöversikt** kan Sammy utföra följande uppgifter:

-   Identifieringen av den matchande inleveransordern och registrera inleveransen som **pågår**. Raderna som krävs för registrering genereras automatiskt och inleveransen kan även övervakas även om transaktionerna inte ännu har bokförts som **registrerade**.
-   Få tillgång till den lämpliga införseljournalreferensen (det vill säga journalen **Artikelinförsel** eller journalen **Produktionsinleverans**) och identifiera journaler som är klara för produktinleveransuppdatering.

## <a name="arrival-overview-page"></a>Sidan Införselöversikt
Öppna sidan **Införselöversikt** genom att klicka på **lagerhantering**&gt;**inkommande order**&gt;**Införselöversikt**. Du kan visa en lista över order som ska inlevereras. Översikten är indelad i en rubrik och rader. Informationen i rubriken grupperas efter ordertyp, förväntat inleveransdatum och leveransdestination. När du väljer en rubrikrad för införsel väljs alla detaljraderna som är relaterade till inleveransreferensen för införsel i området med radinformation på sidan. När alla relaterade journalrader har bokförts, visas inte informationen.

### <a name="arrival-overview-profiles"></a>Översiktsprofiler för införsel

Sidan **Införselöversikt** ger en översikt över artiklar som förväntas levereras och det datum då de förväntas levereras. Som en del av införselprocessen kan flera uppsättningar personliga inställningar användas. Enskilda användare kan definiera sina egna inställningar på sidan **Översiktsprofiler för införsel**.

### <a name="set-up-item-arrival"></a>Ställ in artikelinförsel

I vårt exempel vill Sammy skapa en ny dator på en plats som ska användas för att ta emot färdiga varor som kommer från produktion på Plats 1. På sidan **Översiktsprofiler för införsel** skapar Sammy en ny profil som heter **Plats 1 produktion** och anger följande inställningar.

1.  På snabbfliken **Alternativ för införsel** i fältgruppen **intervall** anger du information om ett dagsintervall och lagerställen som ska inkluderas i översikten.
2.  På snabbflikenden **Införselalternativ** i fältgruppen **journal** anger du mottagande lager, en plats och ett journalnamn (artikelinförsel/produktionsinleverans).
3.  På snabbfliken **Detaljer för fråga om införsel** i fältgruppen **Plats** i fältet **begränsa till plats**, anger du en plats om du vill begränsa vyn i översiktsområdet Översikt.
4.  På snabbfliken **Detaljer för fråga om införsel** i fältgruppen **transaktionstyper som visas** anger du alternativet **tillverkningsorder** till **Ja**.
5.  På snabbfliken **Detaljer för fråga om införsel** på snabbfliken i gruppen **Diverse** ange alternativet **Uppdatera vid start** till **Ja** om vyn ska uppdateras automatiskt vid starten. Ange alternativet **Uppdatera vid intervalländring** till **Ja** om vyn ska uppdateras automatiskt när intervallet har ändrats.

I det här exemplet på fältet **Namn på översiktsprofil för införsel** på snabbfliken **införselalternativ** på sidan **Införselöversikt** anges till **Plats 1 produktion**.

### <a name="prerequisites-for-arrival-journals"></a>Förutsättningar för införseljournaler

Om du vill skapa införseljournaler automatiskt från sidan **Införselöversikt** måste du definiera lämplig information i fältgruppen **journal** på snabbfliken **införselalternativ**.

-   Du måste ange ett journalnamn för att skapa en journal.

[![Ange ett journalnamn](./media/arrival-overview-journal.png)](./media/arrival-overview-journal.png)

-   Om du anger värden i fälten **lagerställe** och **plats** tillämpas värdena på journalraderna. Om du inte anger värden används värdena från dimensionen som anges i lagertransaktionerna.

#### <a name="items-that-are-received-from-one-expected-receipt-order"></a>Artiklar som tas emot från en förväntad inleveransorder

På snabbfliken **inleveranser** väljer Sammy en rad och klickar på **starta införsel**. Alla relaterade rader i det angivna intervallet och som har en kvantitet för att registrera markeras automatiskt. En artikelinförseljournal skapas som har en matchning mellan den förväntade inleveransordern och journalen. Kvantiteten initieras automatiskt på alla rader som har skapats.

#### <a name="items-that-are-received-from-more-than-one-expected-receipt-order"></a>Artiklar som tas emot från mer än en förväntad inleveransorder

På snabbfliken **inleveranser** väljer Sammy flera rader och klickar på **starta införsel**. En artikelinförseljournal skapas som har en matchning mellan alla förväntade inleveransorder och journalen. Alla rader har skapats på ett artikelinförseljournalhuvud och kvantiteten initieras automatiskt.

### <a name="receive-items-from-one-or-more-expected-receipt-orders"></a>Ta emot artiklar från en eller fler förväntade inleveransorder

#### <a name="view-information"></a>Visa information

För en översikt över förväntade inleveranser i ett datumintervall anger Sammy följande information i fälten på snabbfliken **införselalternativ** på sidan **Införselöversikt** och klickar på **uppdatera** för att uppdatera vyn:

-   Namn på översiktsprofil för införsel: **förfrågan**
-   Visa rader: **Alla**
-   Dagar bakåt: (tom)
-   Dagar framåt: **0**
-   Lager: **GW, MW**

Sammy kan också visa följande information:

-   Alla relaterade inleveransorder för systemdatumet och ett obegränsat antal dagar bakåt från (intervallet **InventTrans.StatusDate**) och inleveranser till lagerställen GW och MW, oavsett status.
-   Detaljerad radinformation för fler än en order. Sammy kan markera flera rubrikrader i översikten och klickar sedan på **Visa alla markerade** för att visa all motsvarande raddetaljinformationen för alla valda order.
-   Information om en specifik inköpsorder. Om du vill visa information som är relaterad till ett specifikt referensnummer i översikten kan Sammy ange ett kontonummer i fältet **Kontonummer** och ett ordernummer i fältet **referensnummer**.
-   En översikt över registreringsaktiviteterna som förfaller till betalning för alla orderrader som en artikelinförseljournal har skapats för men ännu inte har bokförts. För att visa den här informationen kan Sammy välja **pågår** i fältet **visa rader**.

### <a name="update-journals"></a>Uppdatera journaler

För att registrera en eller flera orderrader som förfaller till betalning kan Sammy markera raderna i översiktsrutnätet eller radrutnätet och sedan klicka på **journaler** &gt; **visa införsel från inleveranser**. Artikelinförselrubrikerna som matchar raderna visas. För att uppdatera produktinleveransens inköpsorder för registrerade artiklear kan Sammy få åtkomst till de journalrubriker för artikelinförsel som är klara för uppdatering. Om du vill öppna dessa journalrubriker för artikelinförsel klickar du på **journaler** &gt; **Klara journaler för produktinleverans**. Alla rubrikrader som är klara för uppdatering av produktinleverans i det angivna lagerstället visas. (Rubrikrader som visas är inte relaterade till dagsintervallet).

### <a name="start-an-arrival-registration"></a>Starta en införselregistrering

Genom att markera flera rader på sidan **Införselöversikt** kan Sammy börja en inleverans för mer än en inleveransreferens. När han markerar en rad i inleveransöversikten markeras motsvarande raddetaljerna. Om en kvantitet för registrering existerar är knappen **starta införsel** tillgänglig. Sammy kan använda två metoder för att starta införselregistrering:

-   Om du vill filtrera sidan så att den endast visar poster som uppfyller ett visst villkor skannar du ett referensnummer från en leverantör t.ex. streckkoden för en följesedel i fältet **leverantörsreferens**.
-   I översiktsdelen eller informationsdelen på sidan **Införselöversikt** väljer du manuellt eller avbryter markeringen av poster för införselregistrering. Sedan när Sammy klickar på **starta införsel** skapas de valda posterna automatiskt i en artikelinförseljournal. Posterna innehåller radinformationen och all unik fältinformation som har tilldelats.

## <a name="update-arrival-information-and-process-a-product-receipt"></a>Uppdateringsinformation och bearbeta en produktinleverans
När alla artiklar har registrerats uppdaterar lagerchefen eller inköpschefen de inlevererade artiklarna med en produktinleverans som läggs till den fysiska kostnaden. Följ dessa steg för att uppdatera införselinformation och bokföra en produktinleverans.

1.  Klicka på **lagerhantering** &gt; **inkommande order** &gt; **Införselöversikt**.
2.  På sidan **Införselöversikt** klickar du på **journaler** &gt; **klara journaler för produktinleverans** om du vill visa en lista med journaler som är klara för produktinleveransuppdatering.
3.  Välj de journaler som måste uppdateras och klicka sedan på **funktioner** &gt; **produktinleverans**.
4.  På sidan **bokföring** anger du produktinleveransnumret om den inte redan finns i journalen och klickar på **OK** för att bearbeta produktinleveransen.

## <a name="summary"></a>Sammanfattning
Sidan **Införselöversikt** kan hjälpa lagerchefen och lagerarbetare att få en översikter över förväntat arbete som måste utföras av ett inkommande process. Sidan kan också användas för att starta artikelinleveransprocessen för att hjälpa till att garantera att artiklarna spåras i den första posten i lagret.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]