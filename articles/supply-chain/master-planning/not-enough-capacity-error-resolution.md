---
title: Korrigera planeringsmotorfelet "Det finns inte tillräcklig kapacitet"
description: Det här avsnittet innehåller information om orsakerna och lösningarna för planeringsmotorfelet "Produktionsorder %1 kunde inte tidsplaneras. Det finns inte tillräcklig kapacitet".
author: ChristianRytt
ms.date: 7/29/2021
ms.topic: article
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 16626a7ee74e89bd129d8435a17d16b41a5e0387
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565769"
---
# <a name="fix-the-not-enough-capacity-could-be-found-scheduling-engine-error"></a>Korrigera planeringsmotorfelet "Det finns inte tillräcklig kapacitet".

[!include [banner](../includes/banner.md)]

När du kör planering kan följande felmeddelande kan visas:

> Det gick inte att planera produktionsordern %1. Det finns inte tillräcklig kapacitet.

Det finns flera orsaker till att planeringsmotorn kan misslyckas och skicka det här felmeddelandet. Det här avsnittet innehåller riktlinjer som hjälper dig att hitta rotorsaken till felet och sedan begränsa det.

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

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
