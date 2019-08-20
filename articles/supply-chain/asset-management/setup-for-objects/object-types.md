---
title: tillgångstyper
description: Det här avsnittet beskriver hur du skapar tillgångstyper i tillgångshantering. Det beskriver också de element som är relaterade till tillgångstyper.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 288dac77f9d999012ec930ef2bca5c0921c2955f
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783606"
---
# <a name="asset-types"></a>tillgångstyper

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Det här ämnet förklarar hur du skapar tillgångstyper. Det beskriver också de element som är relaterade till tillgångstyper. tillgångstyper används som allmänna kategorier för tillgångar. Exempel är CNC-maskiner, mätutrustning och lastbilsmotorer. tillgångstyper används för att hantera jobbtyper (underhållsuppgifter), livscykeltillstånd för tillgångar, tillgångsmått, tillgångsattribut, mallar för villkorsbedömning och tillgångsmodeller som kan väljas för en tillgång. Du måste ange tillgångstyp när du skapar en tillgång.

För varje tillgångstyp kan variationer av tillgångstypinställningarna skapas. Om du till exempel har en tillgångstyp som heter **lastbilar** kan du skapa varianter av den tillgångstypen för olika tillgångstillverkare och tillgångsmodeller. För varje tillgångstypinställning kan du lägga till nödvändiga reservdelar och underhållsplaner.

Först ställer du in de nödvändiga tillgångstyperna. Därefter skapar du de tillgångsmodeller som ska relateras till tillgångstyperna. Slutligen, på sidan **standardtypen för tillgång** skapar du alla varianter av tillgångstyper som krävs för din utrustning.

## <a name="create-an-asset-type"></a>Skapa en tillgångstyp

1. Välj **tillgångshantering** \> **inställningar** \> **tillgångstyper** \> **tillgångstyper**.
2. Välj **ny** om du vill skapa en tillgångstyp.
3. I fältet **tillgångstyp** anger du tillgångstyp-ID.
4. Ange sedan ett namn i fältet **Namn**.
5. I fältet **livscykelmodell för tillgång** väljer du en modell för tillgångslivscykel. Mer information om livscykeltillstånd för tillgångar och livscykelmodeller finns i [livscykeltillstånd för tillgångar](object-stages.md).
6. Ange alternativet **total** till **ja** om summerade nyckeltal (KPI) ska beräknas för tillgångar som har denna tillgångstyp.
7. Välj **Spara**.
8. På snabbfliken **jobbtyper** väljer du de jobbtyper som ska relateras till tillgångstypen:

    - Om du vill välja en jobbtyp markerar du fältet **Återstående jobbtyper** och väljer sedan högerpilknappen ![högerpilknappen](media/29-setup-for-objects.png) för att flytta den till avsnittet **Valda jobbtyper**.
    - Om du vill välja alla tillgängliga jobbtyper väljer du ![pilen vidarebefordra alla](media/30-setup-for-objects.png). Alla jobbtyper överförs från fältet **återstående jobbtyper** till fältet **valda jobbtyper**.
    - Om du vill avbryta valet av jobbtyp markerar du fältet **Valda jobbtyper** och väljer sedan vänsterpil knappen ![vänsterpil knappen](media/31-setup-for-objects.png) för att flytta den till fältet **Återstående jobbtyper**.

9. Du kan också välja tillgångsmått som ska vara relaterade till tillgångstypen. På snabbfliken **tillgångsmått** gör du dina val med hjälp av metoderna som beskrivs för jobbtyper i steg 8. Mer information om inställning av tillgångsmått finns i [underhållstillgångsmått](counters.md).
10. Du kan också välja attributtyper som ska vara relaterade till tillgångstypen. På snabbfliken **attributtyper** gör du dina val med hjälp av metoderna som beskrivs för jobbtyper i steg 8. Om du vill skapa den önskade sekvensen av attributtyper väljer du en attributtyp de **valda attributtyper** och använder sedan uppåtpil och nedåtpil för att flytta den. Sekvensen av attributtyper visas på tillgångar som använder den här tillgångstypen. Mer information om tillgångsattribut finns i [underhåll attributtyper](../setup-for-functional-locations/specification-types.md).

    > [!NOTE]
    > När du lägger till nya attributtyper på snabbfliken **attributtyper** uppdateras befintliga tillgångar automatiskt med den informationen.

11. Du kan också välja de tillståndsbedömningsmallar som ska vara relaterade till tillgångstypen. På snabbfliken **Tillståndsbedömningar** gör du dina val med hjälp av metoderna som beskrivs för jobbtyper i steg 8. Mer information om villkorbedömningsmallar och registreringar finns i [villkorsbedömning](../setup-for-objects/condition-assessment.md).
12. Snabbfliken **tillgångsmodell** visar alla kombinationer av tillgångstillverkare och -modeller som har ställts in för den valda tillgångstypen. Om du vill se kombinationerna uppdelade efter tillverkare väljer **Tillgångsmodell** för att öppna sidan **Tillgångsmodell**.

    På sidan **Tillgångsmodell** kan du lägga till tillgångsmodell – tillgångstyprelationer. Dessutom på sidan **tillgångstyper** kan du lägga till tillgångstillverkare – tillgångsmodell relationer direkt till en tillgångstyp. Slutligen, på sidan **tillgångsmodell** (**tillgångshantering** \> **inställningar** \> **tillgångar** \> **tillgångsmodell**), kan du skapa en ny tillgångstillverkare – tillgångsmodell – tillgångstyprelationer. Det finns därför tre sätt att ställa in och redigera tillgångstillverkare – tillgångsmodell – tillgångstyprelationer. Alla tillgängliga kombinationer visas från olika perspektiv, och du kan välja önskad ingångspunkt när du arbetar med installationen.

> [!NOTE]
> - Om du väljer tillgångsmått för en tillgångstyp, uppdateras valen automatiskt på sidan **tillgångsmått** (**tillgångshanterings** \> **inställningar** \> **tillgångar** \> **tillgångstyp** \> **tillgångsmått**).
> - Fälten i avsnittet **Detaljer** på snabbfliken **allmänt** visar antalet jobbtyper, tillgångsmått, attribut och så vidare som ställs in för den valda tillgångstypen.

Arbetsorder som skapas manuellt är vanligtvis relaterade till avhjälpande underhåll, medan arbetsorder som skapas automatiskt är relaterade till förebyggande underhåll. När du skapar arbetsorder manuellt kan endast de jobbtyper som har valts på snabbfliken **jobbtyper** på sidan **tillgångstyper** användas. Automatiskt skapade arbetsorder kan dock använda alla jobbtyper som du skapar på sidan **jobbtyper** (**tillgångshantering** \> **inställning** \> **jobb** \> **jobbtyper**).

## <a name="create-asset-type-setup-lines"></a>Skapa inställningsrader för tillgångstyp

1. Välj **tillgångshantering** \> **inställningar** \> **tillgångar** \> **tillgångstyper** \> **inställning av tillgångstyper**. Du kan också **tillgångshantering** \> **inställningar** \> **tillgångar** \> **tillgångstyper** \> **tillgångstyper**, välj en tillgångstyp och välj sedan **inställning av tillgångstyp**.
2. Första gången du använder sidan **inställning av tillgångstyp** kanske du tycker att knappen **skapa kombinationer** är användbar. Du kan använda den här knappen för att snabbt skapa alla kombinationer av en tillgångsmodell på en tillgångstyp. Välj **skapa kombinationer**, välj den tillgångstyp som du vill skapa kombinationer för och välj **OK**.

    > [!NOTE]
    > Om du inte kommer att använda alla kombinationer av tillgångstypinställningar som skapades automatiskt kan du ta bort en inställning genom att markera **ta bort**.

3. Välj **ny** om du vill manuellt vill skapa en inställning av tillgångstyp.
4. Beroende på hur specifika inställningarna för tillgångstypen ska vara, gör du val i fälten **tillgångstyp**, **tillverkare** och **modell**.
5. Om ett garantiavtal är relaterat till tillgångstypen väljer du avtalet i fälten **leverantörsgaranti** och **kundgaranti**. 
6. På snabbfliken **reservdelar** väljer du **Lägg till** för att lägga till reservdelar till den valda inställningen av tillgångstyp.
7. Om du vill godkänna en reservdel väljer du reservdelsraden och väljer sedan **Godkänn**. Du kan välja flera rader för godkännande.
8. Om du vill se om en reservdel används någon annanstans i tillgångshantering (till exempel i relation till tillgångar och arbetsorder), markerar du reservdelsraden och väljer sedan **artikel där den används** för att öppna sidan **artikel där den används**. Om du vill se alla aktiva reservdelar i listan markerar du kryssrutan **aktiv**. Om du bara vill se godkända reservdelar markerar du kryssrutan **godkänd**.
9. På snabbfliken **underhållsplaner** väljer du **Lägg till** för att lägga till underhållsplaner till den valda inställningen av tillgångstyp.
10. Om du vill kopiera en inställning för tillgångstyp till en annan inställning kan du använda funktionen Kopiera. Välj inställning av tillgångstyp för att kopiera en inställning, välj **kopiera inställningar** välj den inställning för tillgångstyp som du vill kopiera inställningarna från. Inställningarna för de olika alternativen avgör hur mycket information som inkluderas. När du är klar väljer du **OK** för att kopiera inställningarna.

> [!NOTE]
> Om du har många reservdelsrader och underhållsplaner som du ska återanvända, kan du med funktionen Kopiera snabbt och enkelt ställa in data för många kombinationer av inställningar av tillgångstyp.

## <a name="spare-parts-on-the-asset-type-setup"></a>Reservdelar på inställning av tillgångstyp

Som beskrevs i avsnittet "Skapa inställningsrader för tillgångstyp" ställs reservdelar in på tillgångsmodeller på sidan **inställning av tillgångsvy**. När du öppnar sidan **inställning av tillgångstyp** visas därför endast de reservdelar som är relaterade till den valda kombinationen av en tillgångstyp, tillgångstillverkare och tillgångsmodell. Om du vill se en lista över alla reservdelsposter öppnar du sidan **reservdelar** (**tillgångshantering** \> **frågor** \> **reservdelar**).

På sidan **reservdelar** kan du också skapa nya reservdelar för befintliga kombinationer av en tillgångstyp, tillgångstillverkare och tillgångsmodell. Du kan bestämma om du vill skapa reservdelsposter på sidan **inställning av tillgångstyp** eller på sidan **reservdelar**. Sidan **inställning av tillgångstyp** ger en översikt över data på den valda kombinationen av en tillgångstyp, tillgångstillverkare och tillgångsmodell medan sidan **reservdelar** ger en fullständig översikt över alla inställningsrader för tillgångstyper. Om sidan **reservdelar** innehåller många poster kan sidan **inställning av tillgångstyp** ge dig en bättre överblick.

Om du vill se om en reservdel på den valda raden används någon annanstans i tillgångshantering (till exempel i relation till tillgångar och arbetsorder), markerar du **artikel där den används** för att öppna sidan **artikel där den används**. 

