---
title: Korrigera planeringsmotorfelet "Det finns inte tillräcklig kapacitet" och begränsad kapacitet
description: Denna artikel innehåller information om orsakerna till och lösningarna för "Produktionsorder %1 kunde inte tidsplaneras. Det finns inte tillräcklig kapacitet".
author: t-benebo
ms.date: 7/29/2021
ms.topic: article
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2db4c2606936222fcd1a97cf2814fbfbc41df113
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891043"
---
# <a name="fix-the-not-enough-capacity-could-be-found-scheduling-engine-error"></a>Korrigera planeringsmotorfelet "Det finns inte tillräcklig kapacitet".

[!include [banner](../includes/banner.md)]

När du kör planering kan följande felmeddelande kan visas:

> Det gick inte att planera produktionsordern %1. Det finns inte tillräcklig kapacitet.

Det finns flera orsaker till att planeringsmotorn kan misslyckas och skicka det här felmeddelandet. Denna artikel innehåller riktlinjer som hjälper dig att hitta grundorsaken till felet och därefter begränsa det.

## <a name="review-the-applicable-resources"></a>Granska tillämpliga resurser

Felet kan inträffa om inga tillämpliga resurser uppfyller åtgärdsbehoven på produktionsorderplatsen.

Följ stegen nedan för att granska tillämpliga resurser.

1. Gå till **Produktionskontroll \> Produktionsorder \> Alla produktionsorder** och öppna eller välj den produktionsorder som inte kan tidsplaneras.
1. I Åtgärdsfönstret, på fliken **Produktionsorder**, i gruppen **Produktionsinformation**, väljer du **Flöde**.
1. På sidan **Produktionsflöde** väljer du åtgärden och väljer sedan **Tillämpliga resurser** i åtgärdsrutan.
1. I dialogrutan **Tillämpliga resurser** ställer du in fältet **Användningskrav för** till *Grovplanering* eller *Finplanering*, beroende på vilken typ av planering du använder.
1. Se till att det finns resurser som kan användas på produktionsorderplatsen.

## <a name="review-the-calendars-that-are-associated-with-resources"></a>Granska de kalendrar som associerade med resurser

Felet kan inträffa om ingen kalender är associerad med resursen eller resursgruppen, eller om den associerade kalendern inte är korrekt konfigurerad (den har till exempel inga arbetstider eller dess effektivitet som en procentsats är 0 \[noll\]).

Följ dessa steg för att kontrollera att en kalender är associerad med resursen eller resursgruppen.

1. Gå till **Produktionskontroll \> Produktionsorder \> Alla produktionsorder** och öppna eller välj den produktionsorder som inte kan tidsplaneras.
1. I Åtgärdsfönstret, på fliken **Produktionsorder**, i gruppen **Produktionsinformation**, väljer du **Flöde**.
1. På sidan **Produktionsflöde** väljer du åtgärden och väljer sedan **Tillämpliga resurser** i åtgärdsrutan.
1. Välj resursen i dialogrutan **Tillämpliga resurser** och välj sedan **Visa resurs**. Du kan även markera och hålla ned (eller högerklicka) i fältet **Resursgrupp** och välja **Visa detaljer**.
1. På snabbfliken **Kalendrar** på sidan **Resurser** eller **Resursgrupper** kontrollerar du att en kalender är associerade med resursen eller resursgruppen.

> [!NOTE]
> Om felet inträffar under grovplaneringen måste du se till att en kalender är associerad med alla tillämpliga resursgrupper.

Följ de här stegen för att granska inställningarna i kalendern.

1. Gå till **Organisationsadministration \> Konfigurera \> Kalendrar \> Kalendrar** och välj den kalender som är associerade med resursen eller resursgruppen.
1. Välj **Arbetstider** i åtgärdsrutan.
1. Se till att sidan **Arbetstider** inte är tom. För de dagar du är intresserad av bör du dessutom kontrollera att fältet **Kontroll** inte har inställningen *Stängt*, att det finns arbetstider och att fältet **Effektivitet är procentandel** inte har inställningen *0* (noll).

Om kalendern är associerad med baskalendern måste du även granska inställningarna för baskalendern.

> [!NOTE]
> I grovplaneringen används resursgruppens kalender för att bestämma start- och sluttider för och datum varje åtgärd. Det begränsar också den tid som systemet kan planera för en specifik åtgärd för en viss dag i en specifik resursgrupp. Om arbetstiderna för en resursgrupp en viss dag till exempel är från 08:00 till 16:00, kan beläggningen som en åtgärd lägger på resursgruppen inte överskrida den beläggning som kan passa in i åtta timmar, oavsett hur mycket tillgänglig kapacitet resursgruppen har den dagen. Tillgänglig kapacitet kan dock ytterligare begränsa beläggningen.

## <a name="review-the-scheduling-parameters"></a>Granska planeringsparametrarna

För att säkerställa bra prestanda söker planeringsmotorn endast efter en resurs under en viss tid och ett specifikt antal tidsplaneringskonflikter.

Följ de här stegen för att granska planeringsparametrarna.

1. Gå till **Organisationsadministration \> Konfigurera \> Planeringsparametrar**.
1. Gör något av följande:

    - Om alternativet **Tidsgräns för tidsplanering aktiverad** har inställningen *Nej* går du vidare till steg 3.
    - Om alternativet **Tidsgräns för tidsplanering aktiverad** har inställningen *Ja* ökar du värdet på fältet **Maximal planeringstid per sekvens** för att bearbetningen ska få mer tid att slutföras.

1. Gör något av följande:

    - Om alternativet **Tidsgräns för optimering av tidsplanering aktiverad** har inställningen *Nej* går du vidare till steg 4.
    - Om alternativet **Tidsgräns för optimering av tidsplanering aktiverad** har inställningen *Ja* ökar du värdet på fältet **Tidsgräns för optimeringsförsök** för att bearbetningen ska få mer tid att slutföras.

1. Om du har ändrat någon av inställningarna på sidan måste du omplanera ordern för att försöka igen.

## <a name="review-capacity"></a>Granska kapacitet

Felet kan inträffa när du gör en begränsad planering, men det inte finns någon ledig kapacitet.

Följ de här stegen om du vill utföra tidsplanering med obegränsad kapacitet.

1. Gå till **Produktionskontroll \> Produktionsorder \> Alla produktionsorder** och välj eller öppna den produktionsorder som inte kan tidsplaneras.
1. I åtgärdsrutan på fliken **Tidsplanera**, i gruppen **Produktionsorder** väljer du **Tidsplanera åtgärder** eller **Tidsplanera jobb**.
1. I dialogrutan **Grovplanering** eller **Finplanering** anger du alternativet **Begränsad kapacitet** till *Nej*.
1. Välj **OK** för att tidsplanera ordern.

Följ stegen nedan för att granska den tillgängliga kapaciteten för resursen.

1. Gå till **Organisationsadministration \> Resurser \> Resurser** och välj en resurs som kan användas för ordern som inte kan tidsplaneras.
1. I åtgärdsrutan på fliken **Resurs**, i gruppen **Visa**, väljer du **Kapacitetsbeläggning** eller **Kapacitetsbeläggning, grafiskt** och kontrollerar att det finns tillgänglig kapacitet.

Följ stegen nedan för att granska den tillgängliga kapaciteten för resursgruppen.

1. Gå till **Organisationsadministration \> Resurser \> Resursgrupper** och välj en resursgrupp som kan användas för ordern som inte kan tidsplaneras.
1. I åtgärdsrutan på fliken **Resursgrupp**, i gruppen **Visa**, väljer du **Kapacitetsbeläggning** eller **Kapacitetsbeläggning, grafiskt** och kontrollerar att det finns tillgänglig kapacitet.

## <a name="master-planning-books-a-resource-when-the-resource-calendar-is-closed"></a>Huvudplaneringsregler för en resurs när resurskalendern är stängd

När du använder grovplanering kommer huvudplaneringen att planerar kapacitet enligt kalendern för den primära resursgruppen. Den bokar den sekundära åtgärden samtidigt som den primära åtgärden och tar inte hänsyn till kalendrarna eller kapaciteten för den sekundära åtgärden. Detta kan leda till att tillverkningsordern planeras på en stängd kalender eller vid en tidpunkt när den sekundära åtgärden är tillgänglig (kalender stängd, ingen kapacitet).

Vid finplanering tar huvudplaneringen hänsyn till kapacitet och kalender för både den primära och sekundära åtgärden vid planering av ordern. Kalendrar för båda åtgärderna måste vara öppna och ha tillgänglig kapacitet för att ordern ska kunna planeras.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
