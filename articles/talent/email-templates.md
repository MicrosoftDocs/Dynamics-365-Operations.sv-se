---
title: E-postmallar
description: "Det här avsnittet ger information om e-postmallarna som du kan skapa och använda i Microsoft Dynamics 365 for Talent - Attract."
author: josaw
manager: AnnBe
ms.date: 10/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 85581968d9d242460117693174acbf906463997f
ms.contentlocale: sv-se
ms.lasthandoff: 10/22/2018

---

# <a name="email-templates"></a>E-postmallar
[!include[banner](../includes/banner.md)]

Genom att använda biblioteket för e-postmallar kan administratörer skapa ett enhetligt tema och profilering för alla e-postmeddelanden som skickas via Microsoft Dynamics 365 for Talent: Attract. Administratörer kan också anordna en samling innehåll för e-postmallar som andra användare kan använda. Anställningsteamet kan använda mallarna i arbetsflödet för att effektivare skicka e-post. Vissa e-postmeddelanden i Attract har konfigurerats att skickas automatiskt och administratören kan använda biblioteket för e-postmallar för att anpassa innehållet för dessa e-postmeddelanden.

## <a name="global-template-configurations"></a>Konfiguration av global mall

För att skapa konsekvent profilering för alla e-postmeddelanden måste administratören först ställa in globalt sidhuvud och sidfot för alla e-postmallar. I Administrationscenter på fliken **Inställningar för e-postmall** i avsnittet **rubrik** kan administratör överföra en bild som ska användas som sidhuvud eller banderoll för alla e-postmeddelanden. Bilden kanske är företagets logotyp, ett brevhuvud eller någon annan representativ bild. Vi rekommenderar att bredden är mellan 25 och 800 pixlar och att höjden är mellan 25 och 150 pixlar, eftersom dessa mått är optimala för de flesta e-postklienter, till exempel Microsoft Outlook. Bilden måste vara en JPEG-, JPG-, PNG- eller SVG-fil och filen får inte vara mindre än 1 megabyte (MB). När en bild har överförts genereras och visas en förhandsgranskning av sidhuvudet. Om sidhuvudets bild måste tas bort eller ersättas, kan administratören använda alternativet **Ta bort** ovanför förhandsgranskningen.

I avsnittet **sidfot** kan administratören ge länkar till företagets sekretesspolicy för kommunikation och till de villkor som gäller. De här länkarna ingår i en sidfot som genereras automatiskt. Därefter visas en förhandsgranskning av den här sidfoten.

Kom ihåg att spara dina ändringar innan du stänger administratörscentret.

> [!NOTE] 
> Sidhuvudet och sidfoten är globala inställningar för alla e-postmeddelanden. Därför visas de i e-postmeddelanden som skickas via Attract. Om inställningarna inte är konfigurerade lämnas sidhuvud- och sidfotstexten utanför alla e-postmeddelanden.

## <a name="email-template-library"></a>Bibliotek för e-postmallar 

När den globala mallkonfigurationer är inställd kan administratör börja skapa och anordna mallar för e-postmeddelanden som skickas från Attract. Biblioteket för e-postmallar är endast tillgänglig för administratörer. För att öppna biblioteket på den huvudsakliga navigeringsmenyn, välj fliken **e-postmallar**. Biblioteket är kategoriserad efter olika aktiviteter i Attract e-post ska skickas för, t.ex tidsplanering, bedömning och skapa jobb. Administratören kan välja en kategori för att visa alla e-posttyper som är kopplade till aktiviteten. Markera exempelvis **tidsplanering** för att visa olika typer av e-post som skickas under planeringsprocessen och alla mallar som är tillgängliga för varje typ av e-post. Varje delavsnitt i en kategori representerar en typ av e-post.

Vissa typer av e-postmeddelandet kan ha fler än en mottagare. I till exempel kategorin **tidsplanering** skickas e-postmeddelanden när du behöver skicka sammanfattning av tidsplanen för intervjuer till både kandidater och intervjuare. Varje avsnitt har två huvudsakliga kolumner: **Malltitel** och **Mottagare**. Varje rad i avsnittet representerar en enda mall för en typ av e-post. En låssymbol visas först i raden för varje mall. Den här symbolen anger att mallen är en standardmall som ingår i Attract och att den inte kan tas bort. Administratören kan använda knappen med tre punkter för alla mallar (**...**) för att duplicera mallen, ange den som standardmall eller ta bort den. När en mall är en standardmall, kan ett av två problem uppstå. Beteendet framgår av brickan eller brickorna som visas på raden för mallen:

- **Standard** – Denna bricka anger att mallen är standardmallen för e-post som skickas och att informationen anges i den när en användare skickar e-post för den specifika typen.
- **Standard** + **Skickas automatiskt** – kombinationen av märken som indikerar att mallen är den aktiva mallen för systemgenererade e-postmeddelanden som skickas automatiskt.

Om du vill redigera en mall markerar du raden och gör ändringar i mallen.

> [!NOTE]
> Varje mottagare av en viss typ av e-postmeddelandet har en standardmall. Alla Attract-standardmallar ställs in som standardmallar tills administratören skapar en ny mall för en viss typ av e-post och anger den som standardmall.

## <a name="create-a-template"></a>Skapa en mall

Om du vill skapa en mall väljer du **+ Ny mall** i övre högra hörnet av biblioteket för e-postmallar. Om du vill välja vilken typ av e-postmeddelande som du skapar väljer du mallen för mottagaren, processen och evenemanget som e-postmeddelandet ska skickas för. Markera sedan **Skapa**.

Mallen öppnas i redigeringsvyn, och du kan ge mallen ett namn. Om mallen t.ex. är avsedd för kandidater från ett universitet i USA men har innehåll på franska kan du ange **Universitet\_USA\_Franska** som rubrik. Rubrik, ämne och brödtext för alla mallar kan stödja andra språk än engelska.

Fältet **Till** för en mall kan inte redigeras, eftersom du redan har markerat mottagaren när mallen skapades.

Kan du lägga till personer såsom **Rekryterare** eller **Anställande chef** till karbonkopiaraden (Cc). När e-postmeddelandet skickas ersätts automatiskt rollerna med lämpliga användare baserat på jobbets kontext.

Ämnesrad och brödtext stöder platshållare. Du kan infoga platshållare genom att skriva **\#** och sedan markera lämplig platshållaren i listrutan som slutförs automatiskt. Lista över tillgängliga platshållare visas till höger på sidan. När e-postmeddelandet skickas ersätts automatiskt platshållarna med lämpliga användare baserat på jobbets kontext och på mottagaren. Exempelvis innehåller en mall för ett e-postmeddelande som skickas till kandidater platshållaren \#{kandidat\_namn}. När e-postmeddelandet skickas till en annan kandidat som heter Cameron, ersätts platshållaren med Camerons namn.

Brödtextredigeraren är en textredigerare som låter dig utföra och formatera text. Du kan också infoga hyperlänkar och ankare.

När du har skapat en mall för en viss typ av e-post, välj knappen med tre punkter (**...**) på raden för mallen och ange den som standardmall.

## <a name="consume-templates"></a>Förbruka mallar

När anställningsteamet skickar ett e-postmeddelande, kan du använda mallar som skapas av administratören. Om flera mallar har skapats för den e-post som en användare skickar, visas en nedrullningsbar lista i arbetsflödet för e-postkomposition. Standardmallen anges automatiskt, men användaren kan välja en annan mall.

> [!NOTE] 
> För e-postmeddelanden som skickas automatiskt, kan du skapa flera mallar. Men endast en mall kan anges som den aktiva mallen. Eftersom processen har utlösts av händelser, kan endast administratören avgöra vilken mall som ska användas baserat på kombinationen av brickorna **Standard** och **Skickas automatiskt** i biblioteket för mallar.

