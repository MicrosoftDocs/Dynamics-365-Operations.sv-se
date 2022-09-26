---
title: Appen Lagersynlighet
description: I denna artikel beskrivs hur du använder appen för Lagersynlighet.
author: yufeihuang
ms.date: 09/15/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 674adb70cc4372a8c5ca8c75ed3ef840d8ec7b79
ms.sourcegitcommit: d2046cad5de570e6302a4390b41881a7ecb12e26
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/15/2022
ms.locfileid: "9520875"
---
# <a name="use-the-inventory-visibility-app"></a>Använda appen Inventory Visibility

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du använder appen för Lagersynlighet.

Lagersynligheten innehåller en modellbaserad app för visualisering. Appen innehåller tre sidor: **Konfiguration**, **Verksamhetens synlighet** och **Lagersammanfattning**. Den har följande värden:

- Den tillhandahåller ett användargränssnitt (UI) för praktisk konfiguration och konfiguration av preliminär reservation.
- De stöder lagerbehållningsfrågor i realtid för olika dimensionskombinationer.
- Den tillhandahåller ett användargränssnitt för bokföring av reservationsförfrågningar.
- Den tillhandahåller en vy av lagerbehållningen för produkter tillsammans med alla dimensioner.
- Den tillhandahåller en lagerbehållningslista för produkter tillsammans med fördefinierade dimensioner.


## <a name="prerequisites"></a>Förutsättningar

Innan du börjar installerar och konfigurerar du tillägget Lagersynlighet enligt beskrivningen i [Installera och konfigurera Lagersynlighet](inventory-visibility-setup.md).

## <a name="open-the-inventory-visibility-app"></a>Öppna appen Lagersynlighet

Du öppnar appen Lagersynlighet genom att logga in i din Power Apps-miljö och öppna **Lagersynlighet**.

## <a name="configuration"></a><a name="configuration"></a>Inställningar

På sidan **Konfiguration** i Lagersynlighet-appen kan du konfigurera behållningskonfigurationen och konfigurationen av preliminär reservation. När tillägget har installerats innehåller standardkonfigurationen en standardkonfiguration för Microsoft Dynamics 365 Supply Chain Management (datakällan `fno`). Du kan granska standardinställningen. Baserat på dina affärsbehov och lagerbokföringskraven i det externa systemet kan du modifiera konfigurationen för att standardisera det sätt på vilket lagerändringar kan bokföras, ordnas och efterfrågas i flera olika system.

Detaljerad information om hur du konfigurerar lösningen finns i [Konfigurera Lagersynlighet](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Verksamhetens synlighet

Sidan **Verksamhetens synlighet** innehåller resultaten av en realtidsfråga om lagerbehållning, baserat på olika dimensionskombinationer. När funktionen *OnHandReservation* är aktiverad kan du också bokföra reservationsbegäranden från sidan **Verksamhetssynlighet**.

### <a name="on-hand-query"></a>Behållningsfråga

Fliken **Behållningsfråga** visar resultaten av en realtidsfråga om lagerbehållning.

När du öppnar fliken **Behållningsfråga** på sidan **Driftsynlighet** kräver systemet dina autentiseringsuppgifter så att det får den ägartoken som krävs för att fråga efter tjänsten Lagersynlighet. Du kan klistra in ägartoken i fältet **BearerToken** och stänga dialogrutan. Du kan sedan bokföra en begäran om behållningsfråga.

Om ägartoken inte är giltig eller har löpt ut måste du klistra in en ny i fältet **BearerToken**. Ange rätt värde för **Kund-ID**, **Klientorganisations-ID**, **Klienthemlighet** och sedan **Uppdatera**. Systemet får automatiskt en ny, giltig ägartoken.

Om du vill bokföra en behållningsfråga anger du frågan i begärandetexten. Använd det mönster som beskrivs i [Fråga genom att använda inläggsmetoden.](inventory-visibility-api.md#query-with-post-method).

![Inställningar för behållningsfråga](media/inventory-visibility-query-settings.png "Inställningar för behållningsfråga")

### <a name="reservation-posting"></a>Reservationsbokföring

Använd fliken **Reservationsbokföring** på sidan **Driftsynlighet** när du bokför en reservationsbegäran. Innan du kan bokföra en reservationsbegäran måste du aktivera funktionen *OnHandReservation*. Mer information om denna funktion och hur du aktiverar den finns i [Reservationer för lagersynlighet](inventory-visibility-reservations.md).

Om du vill bokföra en reservationsbegäran måste du ange ett värde i begärandetexten. Använd det mönster som beskrivs i [Skapa en reservationshändelse](inventory-visibility-api.md#create-one-reservation-event). Välj sedan **Bokför**. Om du vill visa information om begärandesvar väljer du **Visa detaljer**. Du kan också få värdet `reservationId` från svarsdetaljerna.

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Lagersammanfattning

På sidan **lagersammanfattning** ges en lagersammanfattning för produkter tillsammans med alla dimensioner. Det är en anpassad vy för entiteten *Lagerbehållningssumma*. Data för lagersammanfattning synkroniseras regelbundet från Lagersynlighet.

Följ dessa steg för att aktivera sidan **lagersammanfattning** ställa in synkroniseringsfrekvensen:

1. Öppna sidan **Konfiguration**.
1. Öppna fliken **Funktionshantering och inställningar**.
1. Ställ in växlingsknappen för funktionen **OnHandMostSpecificBackgroundService** till *Ja*.
1. När funktionen har aktiverats blir avsnittet **Tjänstekonfiguration** tillgängligt och innehåller en rad för konfigurering av funktionen **OnHandMostSpecificBackgroundService**. Med den här inställningen kan du välja hur ofta lagersammanfattningsdata ska synkroniseras. Använd knapparna **Upp** och **Ned** i kolumnen **Värde** för att ändra tiden mellan synkroniseringar (som kan vara så låg som 5 minuter). Välj sedan **Spara**.

    ![OnHandMostSpecificBackgroundService, inställning](media/inventory-visibility-ohms-freq.png "OnHandMostSpecificBackgroundService, inställning")

1. Välj **Uppdatera konfiguration** för att spara alla ändringar.


> [!NOTE]
> Funktionen *OnHandMostSpecificBackgroundService* spårar bara ändringar i lagerbehållning som inträffat efter det att du aktiverat funktionen. Data för produkter som inte har ändrats sedan du aktiverade funktionen synkroniseras inte från lagertjänstcachen till Dataverse-miljön. Om din sida för **lagersamamnfattning** inte visar all behållningsinformation du förväntar dig öppnar du Supply Chain Management, och går till **Lagerhantering > Periodiska uppgifter > Integrering av lagersynlighet** inaktiverar du batchjobbet och återaktiverar det. Detta utför den första distributionen och all data synkroniseras med entiteten *Lagerbehållningssumma* under närmaste 15 minuter. Om du vill använda funktionen *OnHandMostSpecificBackgroundService* rekommenderar vi att du aktiverar den innan du skapar ändringar i lagerbehållningen och aktiverar batchjobbet **Integrering för lagersynlighet**.

## <a name="preload-a-streamlined-on-hand-query"></a><a name="preload-the-inventory-visibility-onhand-query"></a>Förinläsning av strömlinjeformad behållningsfråga

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: Preview until further notice -->

Supply Chain Management lagrar en stor mängd information om din nuvarande lagerbehållning och gör den tillgänglig för många olika syften. Många dagliga åtgärder och tredjepartsintegrationer behöver dock bara en liten delmängd av dessa detaljer och när systemet ställs in för alla kan det leda till stora datauppsättningar som tar tid att samla och överföra. Därför kan tjänsten Lagersynlighet med jämna mellanrum hämta och lagra en strömlinjeformad uppsättning lagerbehållningsdata för att göra den optimerade informationen kontinuerligt tillgänglig. Informationen om lagerbehållningen filtreras utifrån konfigurerbara affärskriterier för att säkerställa att endast den mest relevanta informationen inkluderas. Eftersom de filtrerade lagerbehållningslistorna lagras lokalt i tjänsten Lagersynlighet och uppdateras regelbundet, har de stöd för snabbåtkomst, dataexport vid behov och strömlinjeformad integration med externa system.

> [!NOTE]
> Den aktuella förhandsgranskningsversionen av den här funktionen kan bara ge förinlästa resultat som omfattar webbplats och plats. Den slutgiltiga versionen av funktionen förväntas låta du välja andra dimensioner för förinläsning med resultaten.

Sidan **Förinläsa sammanfattning av lagersynlighet** ger en vy av entiteten *Behållningsindex av förinläsning av frågeresultat*. Till skillnad från entiteten *lagersammanfattning* ger entiteten *Behållningsindex av förinläsning av frågeresultat* en tillgänglig inventeringslista för produkter tillsammans med valda dimensioner. Lagersynlighet synkroniserar de förinlästa sammanfattningsdata var 15:e minut.

Om du vill visa data på fliken **Förinläsa sammanfattning av lagersynlighet** måste du aktivera funktionen *OnHandIndexQueryPreloadBackgroundService* på fliken **Funktionshantering** på sidan **Konfiguration** och sedan välja **Uppdatera konfiguration** (se även [Konfigurera lagersynlighet](inventory-visibility-configuration.md)).

> [!NOTE]
> Liksom funktionen *OnhandMostSpecificBackgroudService* spårar funktionen *OnHandIndexQueryPreloadBackgroundService* endast ändringar i lagerbehållning som skett efter att du aktiverat funktionen. Data för produkter som inte har ändrats sedan du aktiverade funktionen synkroniseras inte från lagertjänstcachen till Dataverse-miljön. Om din sida för **lagersamamnfattning** inte visar all behållningsinformation du förväntar dig går du till **Lagerhantering > Periodiska uppgifter > Integrering av lagersynlighet** inaktiverar du batchjobbet och återaktiverar det. Detta utför den första distributionen och all data synkroniseras med entiteten *Behållningsindex av förinläsning av frågeresultat* under närmaste 15 minuter. Om du vill använda den här funktionen rekommenderar vi att du aktiverar den innan du skapar ändringar i lagerbehållningen och aktiverar batchjobbet **Integrering för lagersynlighet**.

## <a name="filter-and-browse-the-inventory-summaries"></a><a name="additional-tip-for-viewing-data"></a>Filtrera och bläddra i lagersammanfattningar

Genom att använda det **avancerade filter** som Dataverse tillhandahåller kan du skapa en personlig vy som visar de rader som är av vikt för dig. Med hjälp av de avancerade filteralternativen kan du skapa många olika vyer, från enkla till komplexa. Du kan också lägga till grupperade och kapslade villkor i filtren. Mer information om hur du använder det avancerade filtret finns i [Redigera eller skapa personliga vyer med avancerade filter](/powerapps/user/grid-filters-advanced).

På sidan **Lagersammanfattning** finns tre fält ovanför rutnätet (**Standarddimension**, **Anpassad dimension** och **Mått**) som du kan använda för att kontrollera vilka kolumner som är synliga. Du kan också välja en kolumnrubrik för att filtrera eller sortera det aktuella den kolumnen. I bilden nedan visas vilka fält som visas för dimension, filtrering, resultaträkning och "läs in fler" på sidan **Lagersammanfattning**.

![Sidan Lagersammanfattning.](media/inventory-visibility-onhand-list.png "Sidan Lagersammanfattning")

Eftersom du har fördefinierade dimensioner som används för inläsning av sammanfattningsdata, visar sidan **Förinläsa sammanfattning av lagersynlighet** dimensionsrelaterade kolumner. *Dimensionerna är inte anpassningsbara&mdash;systemet stöder bara webbplats- och platsdimensioner för förinlästa lagerbehållningslistor.* Sidan **Förinläsa sammanfattning av lagersynlighet** ger filter som liknar de för sidan **Lagersammanfattning** förutom att dimensionerna redan har valts. Följande skärmbild belyser filtreringsfälten som är tillgängliga på **Förinläsa sammanfattning av lagersynlighet**.

![Sidan Förinläsa sammanfattning av lagersynlighet.](media/inventory-visibility-preload-onhand-list.png "Sidan Förinläsa sammanfattning av lagersynlighet")

Längst ned på sidorna **Förinläsa sammanfattning av lagersynlighet** och **Lagersammanfattning** hittar du information som "50 poster (29 valda)" eller "50 poster". Denna information refererar till de poster som läses in för närvarande från resultatet av det **avancerade filtret**. Texten "29 markerade" syftar på antalet poster som har markerats med hjälp av kolumnrubrikfiltret för de inlästa posterna. Det finns också knappen **Läs in fler** som du använder för att läsa in fler poster från Dataverse. Standardantalet poster som läses in är 50. När du väljer **Läs in fler** läses nästa 1 000 tillgängliga poster in i vyn. Siffran på knappen **Läs in fler** visar de poster som för närvarande lästs in samt det totala antalet poster för resultatet för det **avancerade filtret**.
