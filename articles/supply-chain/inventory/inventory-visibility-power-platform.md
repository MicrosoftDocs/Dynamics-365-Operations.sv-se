---
title: Appen Lagersynlighet
description: I detta ämne beskrivs hur du använder appen för Lagersynlighet.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 359f89f98ca6954a0bbafd63fffa1d505a43f0c8
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8060982"
---
# <a name="use-the-inventory-visibility-app"></a>Använda appen Lagersynlighet

[!include [banner](../includes/banner.md)]


I detta ämne beskrivs hur du använder appen för Lagersynlighet.

Lagersynligheten innehåller en modellbaserad app för visualisering. Appen innehåller tre sidor: **Konfiguration**, **Verksamhetens synlighet** och **Lagersammanfattning**. Den har följande värden:

- Den tillhandahåller ett användargränssnitt (UI) för praktisk konfiguration och konfiguration av preliminär reservation.
- De stöder lagerbehållningsfrågor i realtid för olika dimensionskombinationer.
- Den tillhandahåller ett användargränssnitt för bokföring av reservationsförfrågningar.
- Den tillhandahåller en anpassad vy av lagerbehållningen för produkter tillsammans med alla dimensioner.

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

När du väljer fliken **Behållningsfråga** begär systemet dina autentiseringsuppgifter så att det får den ägartoken som krävs för att fråga efter tjänsten Lagersynlighet. Du kan klistra in ägartoken i fältet **BearerToken** och stänga dialogrutan. Du kan sedan bokföra en begäran om behållningsfråga.

Om ägartoken inte är giltig eller har löpt ut måste du klistra in en ny i fältet **BearerToken**. Ange rätt värde för **Kund-ID**, **Klientorganisations-ID**, **Klienthemlighet** och sedan **Uppdatera**. Systemet får automatiskt en ny, giltig ägartoken.

Om du vill bokföra en behållningsfråga anger du frågan i begärandetexten. Använd det mönster som beskrivs i [Fråga genom att använda inläggsmetoden.](inventory-visibility-api.md#query-with-post-method).

![Inställningar för behållningsfråga](media/inventory-visibility-query-settings.png "Inställningar för behållningsfråga")

### <a name="reservation-posting"></a>Reservationsbokföring

Använd fliken **Bokföring av** när du bokför en reservationsbegäran. Innan du kan bokföra en reservationsbegäran måste du aktivera funktionen *OnHandReservation*. Mer information om denna funktion finns i [Reservationer för lagersynlighet](inventory-visibility-reservations.md).

Om du vill bokföra en reservationsbegäran måste du ange ett värde i begärandetexten. Använd det mönster som beskrivs i [Skapa en reservationshändelse](inventory-visibility-api.md#create-one-reservation-event). Välj sedan **Bokför**. Om du vill visa information om begärandesvar väljer du **Visa detaljer**. Du kan också få värdet `reservationId` från svarsdetaljerna.

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Lagersammanfattning

**Lagersammanfattning** är en anpassad vy för entiteten *Inventory OnHand Sum*. Den ger en lagersammanfattning för produkter tillsammans med alla dimensioner. Data för lagersammanfattningen synkroniseras regelbundet från Lagersynlighet. Innan du kan se data på fliken **Lagersammanfattning** måste du aktivera funktionen *OnHandMostSpecificBackgroundService* på fliken **Funktionshantering**.

Genom att använda det **avancerade filter** som Dataverse tillhandahåller kan du skapa en personlig vy som visar de rader som är av vikt för dig. Med hjälp av de avancerade filteralternativen kan du skapa många olika vyer, från enkla till komplexa. Du kan också lägga till grupperade och kapslade villkor i filtren. Mer information om hur du använder det **avancerade filtret** finns i [Redigera eller skapa personliga vyer med avancerade filter](/powerapps/user/grid-filters-advanced).

Högst upp i den anpassade vyn finns tre fält: **Standarddimension**, **Anpassad dimension** samt **Mått**. Du kan använda dessa fält för att kontrollera vilka kolumner som är synliga.

Du kan välja kolumnrubriken för att filtrera eller sortera det aktuella resultatet.

Längst ned i den anpassade vyn visas information som "50 poster (29 valda) eller "50 poster". Denna information refererar till de poster som läses in för närvarande från resultatet av det **avancerade filtret**. Texten "29 markerade" syftar på antalet poster som har markerats med hjälp av kolumnrubrikfiltret för de inlästa posterna.

Längst ned i vyn finns knappen **Läs in fler** som du använder för att läsa in fler poster från Dataverse. Standardantalet poster som läses in är 50. När du väljer **Läs in fler** läses nästa 1 000 tillgängliga poster in i vyn. Siffran på knappen **Läs in fler** visar de poster som för närvarande lästs in samt det totala antalet poster för resultatet för det **avancerade filtret**.

![Lagersammanfattning](media/inventory-visibility-onhand-list.png "Lagersammanfattning")
