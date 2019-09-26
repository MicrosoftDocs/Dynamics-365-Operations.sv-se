---
title: Ställ in prioriterade underhållsarbetare
description: I det här avsnittet beskrivs hur du ställer in prioriterade underhållsarbetare i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f26be81e7057d0cea1473d81452216251633ad9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887421"
---
# <a name="preferred-maintenance-workers"></a>Prioriterade underhållsarbetare

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Du kan göra en inställning för hur underhållsarbetare allokeras för att slutföra arbetsorder under tidsplaneringen av arbetsordern. Användningen av den här funktionen är valfri, men den kan hjälpa dig att göra ett val för den mest kvalificerade underhållsarbetaren för att slutföra ett jobb, baserat på arbetarnas färdigheter och kompetenser. Under tidsplaneringen av arbetsordern används därför inställningarna i **Prioriterade underhållsarbetare** för att fastställa om en viss underhållsarbetare eller arbetargrupp ska tidsplaneras för en arbetsorder. Endast underhållsarbetare som är tillgängliga vid planeringstiden tidsplaneras. Om en förinställd inställning för underhållsarbetare matchar en arbetsorder under planeringen, men underhållsarbetaren allokeras till andra jobb, planeras arbetsordern till en annan, tillgänglig, underhållsarbetare.

Innan du kan ställa in prioriterade underhållsarbetare måste du först ställa in underhållsarbetare och arbetargrupper som ska vara tillgängliga för val. Information om hur du ställer in underhållsarbetare och arbetargrupper finns i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-preferred-workers"></a>Ställa in prioriterade arbetare

En prioriterad underhållsarbetare eller arbetargrupp kan relateras till en viss

- handel  
- variant för typen av underhållsjobb  
- underhållsjobbtyp  
- kategori för typ av underhållsjobb  
- tillgång  
- tillgångstyp  

eller en kombination av dessa urval. Ju fler val du gör för samma post, desto mer specifika blir inställningarna.

1. Klicka på **Tillgångshantering** > **Inställningar** > **Arbetare** > **Prioriterade underhållsarbetare**.

2. Klicka på **Ny** om du vill skapa en ny post.

3. Börja med att skapa en "standardinställning" för underhållsarbetare eller arbetargrupp som inte har några val i fälten som visas i punktlistan ovan. Det innebär att du bara gör ett val i fältet **Prioriterad underhållsarbetargrupp** eller fältet **Prioriterad underhållsarbetare**. I bilden nedan visas ett exempel i den första posten där "Begäranden" har valts som prioriterad underhållsarbetargrupp.

>[!NOTE]
>Standardinställningen kommer att användas vid schemaläggning av arbetsorder om ingen annan, mer specifik kombination matchar innehållet i arbetsordern under schemaläggningen av arbetsorder.

4. Upprepa steg 2 för att skapa en ny post. Gör de val som krävs, beroende på detaljnivån för den prioriterade arbetaren eller arbetargruppen. *Exempel:* I den sjätte posten i bilden nedan väljs underhållsarbetaren Shawn Richardson som prioriterad arbetare. Han väljs automatiskt under tidsplaneringen av en arbetsorder som innehåller tillgången CH-BP1-03-02 och underhållsjobbtypen "Lokalbedömning", om han är tillgänglig vid den schemalagda tiden.

>[!NOTE]
>När en prioriterad underhållsarbetare väljs under arbetsorderplaneringen går Tillgångshantering igenom alla poster för **Prioriterade underhållsarbetare** för att söka efter en eventuell matchning, och kontrollerar alltid den mest specifika kombinationen först. Om det inte går att hitta någon matchning används "standard"-posten med ett val i fältet **Prioriterad underhållsarbetargrupp** eller fältet **Prioriterad underhållsarbetare**.


![Figur 1](media/02-work-order-scheduling.png)

Du kan också ställa in ansvariga underhållsarbetare som kan väljas när en begäran om underhåll eller en arbetsorder skapas. I **Alla arbetsorder** och **Alla underhållsbegäranden** kan du redigera urvalet om det behövs. Mer information finns i [Ansvariga underhållsarbetare](../setup-for-maintenance-requests/responsible-workers.md).

Under tidsplaneringen av arbetsordern beräknas olika poäng för att fastställa vilka arbetare som ska utföra jobben som hör till en arbetsorder (dessa poäng ställs in i **Parametrar för tillgångshantering** > **länken Schemaläggning av arbetsorder**). Om två eller fler prioriterade underhållsarbetare eller ansvariga underhållsarbetare får samma poäng vid tidsplaneringen av arbetsordern väljs en av dem slumpmässigt. I annat fall är det alltid arbetaren med högst poäng som allokeras för att slutföra en arbetsorder.
