---
title: Skapa omallokering av artiklar för kort plockning
description: I det här ämnet visas hur du auktoriserar lagerarbetare att snabbt söka efter alternativa platser om det inte finns tillräckligt med lagerutrymme på den plats som de har hänvisats till.
author: ShylaThompson
manager: tfehr
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e8f5c23f82e96145f411ec993f766a90137b5b8
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438023"
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