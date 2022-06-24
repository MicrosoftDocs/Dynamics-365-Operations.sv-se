---
title: Skapa omallokering av artiklar för kort plockning
description: I denna artikel visas hur du auktoriserar lagerarbetare att snabbt söka efter alternativa platser om det inte finns tillräckligt med lagerutrymme på den plats som de har hänvisats till.
author: Mirzaab
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4e6d7f9b09434346cb0f3670d10437ef8197822
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875026"
---
# <a name="set-up-short-picking-item-reallocation"></a>Skapa omallokering av artiklar för kort plockning

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du auktoriserar lagerarbetare att snabbt söka efter alternativa platser om det inte finns tillräckligt med lagerutrymme på den plats som de har hänvisats till. 

Omallokeringsprocessen styrs av ett **arbetsundantag** och används av lagerställets **arbetare**.

Det går att använda automatiska, manuella eller båda omallokeringsprocesser:

- Automatiska omallokeringar – Platsdirektiv används för att fastställa om varorna finns tillgängliga på en annan plats. Om möjligt kommer arbetet att uppdateras och lageranvändaren kommer att dirigeras till den alternativa platsen.
- Manuell omallokering – Gör att lageranvändaren kan välja mellan en eller flera platser med icke reserverade kvantiteter av varor. 
- Automatisk och manuell – Om systemet inte kan utföra automatisk omallokering och platser är tillgängliga med icke reserverade kvantiteter, uppmanas användaren att välja en plats.

## <a name="set-up-work-exceptions"></a>Konfigurera arbetsavvikelser
Det går att definiera flera arbetsundantag med olika artikelomallokeringspolicyer om du vill göra det möjligt för lagerarbetare att välja en baserat på behoven hos den försändelse som de bearbetar.

Demonstrationsdataföretaget USMF har använts för att skapa denna procedur.

1. I **navigeringsfönstret**, gå till **Lagerstyrning > Inställningar > Arbete > Arbetsundantag**.
2. Klicka på **Ny**. 
3. Ange ett värde i fältet **Kod för arbetsundantag.** Detta är rubriken på detta undantag. Till exempel "Kortplockning manuellt".
4. I fältet **Beskrivning** anger du ett värde. En kort beskrivning av hur detta undantags används. T.ex. är den här artikeln för kortplockning inte tillgänglig.
5. I typfältet **Undantag** välj **Kort plockning**.
6. Välj kryssrutan **Justera lager**. Om detta väljs kommer lagret justeras automatiskt till 0 på en kort plockad plats.
7. Ange eller välj ett värde i fältet **Kod för standardjusteringstyp**. I USMF kan du till exempel välja **Ta bort Res Adj Out**. Varje justerings typ kod innehåller fyra kännetecken: namn, beskrivning, lagerjournalnamn och **Ta bort reservationer**. Om **ta bort reservationer** är aktiverad tas reservationer för den kortplockade orderraden bort.  
8. I fältet **Omallokering av artikel** väljer du ett värde, t.ex. Manuell. Om du väljer manuellt, eller automatiskt och manuellt, måste lagerställearbetaren auktoriseras för att använda manuell omallokering.

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>Ställ in en arbetare som ska använda manuell artikelomallokering

Demonstrationsdataföretaget USMF har använts för att skapa denna procedur.

1. Stäng sidan.
2. I **navigeringsfönstret**, gå till **Lagerstyrning > Inställningar > Arbetare**.
3. Klicka på **Redigera**.
4. I listan väljer du arbetare. Till exempel Julia Funderburk.
5. Expandera snabbfliken **Användare**.
6. I listan väljer du **Användar-ID**. Exempelvis 24.
7. Expandera snabbfliken **Arbete**.
8. Välj **Ja** i fältet **Tillåt manuell omallokering av artikel**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]