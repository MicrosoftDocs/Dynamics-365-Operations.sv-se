---
title: Anpassa stegtitlar och instruktioner för mobilappen Warehouse Management
description: I detta ämne beskrivs hur du skapar och visar anpassade instruktioner för varje enskilt steg i respektive uppgiftsflöde som du konfigurerar in för mobilappen Warehouse Management.
author: Mirzaab
ms.date: 08/11/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-11
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ffd433427b2c5011740a7ee54c93713689945df3
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2021
ms.locfileid: "7902257"
---
# <a name="customize-step-titles-and-instructions-for-the-warehouse-management-mobile-app"></a>Anpassa stegtitlar och instruktioner för mobilappen Warehouse Management

> [!IMPORTANT]
> Funktionerna som beskrivs i detta ämne gäller bara den nya mobilappen Warehouse Management. De påverkar inte den gamla lagerställeappen, som nu har blivit inaktuell.

I detta ämne beskrivs hur du skapar och visar anpassade instruktioner för varje enskilt steg i varje enskilt uppgiftsflöde som du konfigurerar in för mobilappen Warehouse Management. När lagerarbetare får välskrivna instruktioner kan de omedelbart börja använda nya flöden utan behov av föregående utbildning. Denna funktion har följande fördelar:

- **Förbättra medarbetare snabbare genom att låta dem följa enkla instruktioner för respektive uppgiftssteg.** Varje steg i ett flöde tillhandahåller instruktioner som gör det möjligt för medarbetare i frontlinjen att förstå uppgiften.
- **Ge instruktioner som matchar dina egna processer.** Skriv dina egna instruktioner som matchar dina affärs- och lagerställeprocesser. Du kan till exempel anpassa terminologin efter ditt fysiska utrymme och dina lokala förkortningar.

## <a name="turn-on-the-warehouse-app-step-instructions-feature"></a>Aktivera steginstruktionsfunktionen för lagerställeappen

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Warehouse management*
- **Funktionsnamn:** *Steginstruktioner för lagerapp*

## <a name="step-titles-and-step-instructions-in-the-app"></a>Stegtitlar och steginstruktioner i appen

Varje steg i ett uppgiftsflöde i mobilappen Warehouse Management identifieras med ett steg-ID. Varje steg har dessutom en rubrik, en ikon och en instruktion. (Mer information finns i [Tilldela stegikoner och rubriker för mobilappen Warehouse Management](step-icons-titles.md).)

### <a name="step-titles"></a>Stegtitlar

En *stegrubrik* är en kort beskrivning av vad en medarbetare bör göra under ett steg. Den visas som stor text högst upp på skärmen, på det sätt som visas i illustrationen nedan.

![Exempel på en stegrubrik i mobilappen för Warehouse Management](media/wma-step-title.png "Exempel på en stegrubrik i mobilappen Warehouse Management")

> [!TIP]
> På grund av den stora textstorleken bör du försöka hålla stegtitlar så korta som möjligt. I annat fall kan texten komma att kapas. För längre titlar kan emellertid medarbetare fortfarande trycka på och hålla rubriken för att visa en dialogruta visas med den fullständiga texten.

### <a name="step-instructions"></a>Stegvisa instruktioner

En *steginstruktion* är en lång beskrivning som ger mer information om vad en medarbetare ska göra under ett visst steg. Den visas i en popup-dialogruta, på det sätt som visas i illustrationen nedan.

![Exempel på en steginstruktion i mobilappen Warehouse Management](media/wma-step-instructions.png "Exempel på en steginstruktion i mobilappen Warehouse Management")

Steginstruktionen visas automatiskt när ett steg öppnas. En medarbetare kan avvisa den genom att trycka var som helst utanför popup-fönstrets dialogruta. Dialogrutan innehåller dessutom en **Visa inte igen**-kryssruta som medarbetarna kan välja i syfte att förhindra att instruktionen visas nästa gång de utför samma uppgift.

## <a name="load-the-default-setup"></a>Läs in standardinställningarna

När du först aktiverar funktionen *Steginstruktioner för distributionslagerappen* kommer ditt system inte att innehålla några anpassningsbara stegtitlar eller instruktioner. Därför är det första du bör göra att läsa in standardinställningarna. Standardinställningen ger text till alla tillgängliga stegidentifierare på alla språk som stöds. Läs in standardinställningarna genom att följa dessa steg.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Steg för mobil enhet**.
1. Klicka på **Skapa standardinställning** i åtgärdsfönstret. Sidan fylls i med standardstegen.

## <a name="customize-step-titles-and-instructions"></a>Anpassa stegrubriker och instruktioner

Anpassa rubriken och/eller instruktionen för ett steg på valfritt antal språk genom att följa dessa steg.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Steg för mobil enhet**.

    Sidan **Steg för mobil enhet** visar en lista över alla steg som är tillgängliga för ditt system. Varje steg-ID kan delas bland valfrit tantal menyalternativ för mobila enheter. Om ett steg-ID delas mellan flera olika menyalternativ visas samma rubrik och instruktioner för alla dessa menyalternativ. Du kan emellertid skapa åsidosättningar om du vill anpassa rubriken och instruktionen för specifika menyalternativ. (Mer information finns i nästa avsnitt.)

    Rutnätet innehåller följande kolumner:

    - **Menyalternativnamn** – Rader där kolumnen är tom använder den standardstegsrubrik och -instruktion som gäller för alla menyalternativ på mobila enheter som ingen åsidosättning har definierats för. Rader där den här kolumnen är inställd på namnet på ett menyalternativ har åsidosättningar som endast gäller för det angivna menyalternativet.
    - **Steg-ID** – Stegets unika ID.
    - **Rubrik för inmatning** – Den rubrik som visas när programmet begär ny information. Vanligtvis är fälten på sidan tomma (det vill säga, de har inga förinställda värden).
    - **Rubrik för bekräftelse** – Den rubrik som visas när programmet begär bekräftelse på ett värde som redan finns lagrat i systemet. Vanligtvis har fälten på sidan förinställda värden.

1. Hitta kombinationen av värden för **Steg-ID** och **Namn på menyalternativ** som du vill redigera, och välj sedan värdet i kolumnen **Steg-ID**. På den sida som öppnas visas alla tillgängliga översättningar av rubriken och instruktionerna för det valda steget.
1. Följ ett av dessa steg när du vill anpassa texten för valfritt språk. Med båda alternativen kan du redigera texter för befintliga språk. Bara det första alternativet låter dig emellertid lägga till texter för nya språk, medan det andra alternativet bara låter dig visa och redigera texter för alla befintliga menyspecifika åsidosättningar för det valda språket.

    - I verktygsfältet väljer du **Lägg till** om du vill öppna en dialogruta där du kan lägga till och redigera texter för alla språk som stöds. Ange fältet **Referensspråk** som det språk som du vill visa värden för. Värdena visas i den vänstra kolumnen. Ange fältet **Översättningsspråk** som det språk som du vill lägga till eller anpassa. I höger kolumn redigerar du värdena för fälten **Rubrik för inmatning**, **Instruktion för inmatning**, **Rubrik för bekräftelse** och **Instruktion för bekräftelse** efter behov. Välj sedan **OK**.
    - Sök och markera raden i rutnätet där fältet **Språk** är inställt på det språk du vill redigera. I verktygsfältet väljer du **Visa &lt;språk&gt; översättningar i detta steg** för att öppna ett dialogfönster där du kan redigera texter för samtliga tillgängliga åsidosättanden för valt språk. Dialogrutan innehåller ett rutnät med rader för båda standardtexterna (där fältet **Namn på menyalternativ** är tomt) samt för samtliga tillgängliga åsidosättandetexter (där **Namn på menyalternativ** anges som namnet på det menyalternativ som åsidosättandet gäller). Redigera värdena i fälten **Rubrik för inmatning**, **Instruktion för inmatning**, **Rubrik för bekräftelse** och **Instruktion för bekräftelse** efter behov. Välj sedan **OK**.

1. Fortsätt arbetet tills du har definierat alla nödvändiga titlar och instruktioner för alla nödvändiga språk.

## <a name="add-menu-specific-overrides"></a>Lägg till menyspecifika åsidosättningar

Som nämndes i föregående avsnitt kan du skapa valfritt antal menyspecifika åsidosättningar för varje steg-ID. Du kan använda denna funktion för att redigera och ändra instruktionen så att den bättre passar din lokala verksamhetsprocess för ett specifikt menyalternativ. När det gäller till exempel gäller försäljningsplock och ditt företag vanligtvis tillhandahåller arbets-ID:n till arbetare på ett utskrivet dokument, kan du ge en liten antydan om att arbetarna bör börja sitt arbete genom att skanna ett arbets-ID.

Varje åsidosättning gäller för ett specifikt menyalternativ på den mobila enheten och kan innehålla valfritt antal översättningar. Om det inte finns någon åsidosättning för ett menyalternativ används standardtexterna i menyalternativet. Om ingen åsidosättningsöversättning har definierats för ett språk används standardtexterna, även för menyalternativ där åsidosättningen har definierats för andra språk.

Följ stegen nedan om du vill skapa och konfigurera en åsidosättning.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Steg för mobil enhet**.
1. Sök efter och markera den rad som du vill skapa en åsidosättning för i rutnätet.
1. Klicka på **Lägg till stegkonfiguration** i åtgärdsfönstret.
1. I dialogrutan **Lägg till stegkonfiguration** i slistrutan anger du fältet **Menyalternativ** som namnet på det menyalternativ för den mobila enhet som din åsidosättning avser. Välj sedan **OK**.
1. På den sida som visas anges alla texter som är tillgängliga för den nya åsidosättningen. Inledningsvis skapas bara ett (1) språk. Alla andra språk fortsätter att använda standardtexterna såvida du inte lägger till dessa språk här. Redigera texterna och lägg till nya språk efter behov, på det sätt som beskrivs i det föregående avsnittet.
