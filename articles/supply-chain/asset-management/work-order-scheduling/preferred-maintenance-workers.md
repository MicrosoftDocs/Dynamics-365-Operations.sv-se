---
title: Ställ in prioriterade underhållsarbetare
description: I det här avsnittet beskrivs hur du ställer in prioriterade underhållsarbetare i Tillgångshantering.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkerPreferred
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5b044e4616555559be51b0846327b1d55bfe47b3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822549"
---
# <a name="set-up-preferred-maintenance-workers"></a>Ställ in prioriterade underhållsarbetare

[!include [banner](../../includes/banner.md)]

 

Under schemaläggning av arbetsorder kan du göra en inställning för hur underhållsarbetare eller arbetargrupper allokeras för att slutföra arbetsordern. Användningen av den här funktionen är valfri, men den kan hjälpa dig att göra ett val för den mest kvalificerade underhållsarbetaren för att slutföra ett jobb, baserat på arbetarnas färdigheter och kompetenser. Endast underhållsarbetare som är tillgängliga vid planeringstiden tidsplaneras. Om en förinställd inställning för underhållsarbetare matchar en arbetsorder under planeringen, men underhållsarbetaren allokeras till andra jobb, planeras arbetsordern till en annan, tillgänglig, underhållsarbetare.

Innan du kan ställa in prioriterade underhållsarbetare måste du först ställa in underhållsarbetare och arbetsgrupper. Information om hur du ställer in underhållsarbetare och arbetargrupper finns i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-preferred-workers"></a>Ställa in prioriterade arbetare

En prioriterad underhållsarbetare eller arbetargrupp kan relateras till en eller flera av följande:

- handel  
- variant för typen av underhållsjobb  
- underhållsjobbtyp  
- kategori för typ av underhållsjobb  
- tillgång  
- tillgångstyp  

Ju fler val du gör för samma post, desto mer specifika blir inställningarna.

1. Klicka på **Tillgångshantering** > **Inställningar** > **Arbetare** > **Prioriterade underhållsarbetare**.

2. Klicka på **Ny** om du vill skapa en ny post.

3. Börja med att skapa en "standard" underhållsarbetare eller arbetsgrupp. Det innebär att du bara gör ett val i fältet **Prioriterad underhållsarbetargrupp** eller fältet **Prioriterad underhållsarbetare**. I skärmbilden nedan visas ett exempel i den första posten där "Begäranden" har valts som **Prioriterad underhållsarbetargrupp**.

    [!NOTE] Den här standardinställningen kommer att användas vid schemaläggning av arbetsorder om ingen annan, mer specifik kombination matchar innehållet i arbetsordern.

4. Upprepa steg 2 för att skapa en ny post. Gör de val som krävs, beroende på detaljnivån för den prioriterade arbetaren eller arbetargruppen. 

    *Exempel:* I skärmbilden nedan väljs underhållsarbetaren Shawn Richardson som prioriterad arbetare. Han väljs automatiskt under tidsplaneringen av en arbetsorder som innehåller tillgången CH-BP1-03-02 och underhållsjobbtypen "Lokalbedömning", om han är tillgänglig vid den schemalagda tiden.

    [!NOTE] När en prioriterad underhållsarbetare väljs under arbetsorderplaneringen går Tillgångshantering igenom alla poster för **Prioriterade underhållsarbetare** för att söka efter en eventuell matchning, och kontrollerar alltid den mest specifika kombinationen först. Om det inte går att hitta någon matchning används "standard"-posten med ett val i fältet **Prioriterad underhållsarbetargrupp** eller fältet **Prioriterad underhållsarbetare**.

![Figur 1](media/02-work-order-scheduling.png)

Du kan också ställa in *ansvariga* underhållsarbetare som kan väljas när en begäran om underhåll eller en arbetsorder skapas. Du kan redigera valet i **Alla arbetsorder** och **Alla underhållsbegäranden** om det behövs. Mer information finns i [Ansvariga underhållsarbetare](../setup-for-maintenance-requests/responsible-workers.md).

Under tidsplaneringen av arbetsordern beräknas olika poäng för att fastställa vilka arbetare som ska utföra jobben som hör till en arbetsorder (dessa poäng ställs in i **Parametrar för tillgångshantering** > **länken Schemaläggning av arbetsorder**). Om två eller fler prioriterade underhållsarbetare eller ansvariga underhållsarbetare får samma poäng vid tidsplaneringen av arbetsordern väljs en av dem slumpmässigt. I annat fall är det alltid arbetaren med högst poäng som allokeras för att slutföra en arbetsorder.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]