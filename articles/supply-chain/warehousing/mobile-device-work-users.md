---
title: Användarkonton för mobil enhet
description: I det här avsnittet beskrivs hur du ställer in och hanterar användarkonton där arbetare kan logga in och använda programmet Lagerställe.
author: Mirzaab
ms.date: 09/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-09-15
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c4cb36160e692cc12140b57037d2c9739f7b2ebd
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462682"
---
# <a name="mobile-device-user-accounts"></a>Användarkonton för mobil enhet

[!include [banner](../includes/banner.md)]

Varje gång en arbetare börjar använda lagerställeappen måste han eller hon logga in med ett användarnamn och lösenord. Val av antal lagerställeappanvändare kan associeras med varje arbetare i systemet, och lagerställen associeras normalt med var och en av dessa lagerställeappanvändare. Olika alternativ konfigureras också för varje arbetare, för att skapa standardinställningar och andra inställningar som är relevanta för användningen av lagerställeprogrammet.

## <a name="set-up-the-required-worker-and-employee-records"></a>Ställa in de arbets- och medarbetarposter som krävs

Innan du kan ställa in användare av lagerställe-program måste varje arbetare redan finnas som en medarbetare eller anställd i Supply Chain Management i modulen **Personal**.

## <a name="set-up-mobile-device-user-accounts"></a><a name="set-wma-users"></a>Ställ in användarkonton för mobil enhet

När de anställda och medarbetarna har ställts in i Personal kan du tilldela appanvändare för lagerställen till var och en av dem och ställa in andra alternativ som påverkar hur de kan använda programmet.

1. Gå till **Warehouse management \> Inställningar \> Arbetare**.
1. Om du vill redigera en befintlig arbetare markerar du den i listfönstret. För att lägga till en ny post, välj **Ny** i åtgärdsfönstret.
1. Om du ställer in en ny arbetare gör du så här:

    1. I fältet **Arbetare** väljer du målanvändaren i listan med medarbetare.
    1. Välj **Välj**.
    1. Klicka på **Spara** i åtgärdsfönstret.

1. En standardprofil kan användas för att vägleder lagerarbetaren vid förpackningsprocessen som krävs där. Alternativt kan standardprofilen användas om du vill spara de önskade profilinställningarna för arbetaren. På snabbfliken **Profil** anger du följande fält:

    - **Förpackningspolicy för behållare** – Välj en förpackningspolicy för behållare som definierar hur behållare vid förpackningsenheten ska bearbetas. Förpackningspolicyn för behållare som har valts här väljs för arbetaren när han eller hon öppnar förpackningsbehållaren. Mer information finns i följande blogginlägg: [Förbättrad förpackningsfunktion](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611),
    - **Förpackningsprofil-ID** – Välj ett förpackningsprofil-ID som definierar de förpackningspolicy- och behållarinställningar som används. Om det valda förpackningsprofil-ID:t är kopplat till en förpackningspolicy för behållare kan du inte ändra inställningen för **förpackningspolicy för behållare** på den här sidan.

1. På snabbfliken **Standard förpackningsstation** kan du ange följande fält för att definiera vilken standardförpackningsstation som ska tillämpas när arbetaren loggar in. Arbetaren kan fortfarande välja en annan förpackningsstation enligt behov.

    - **Plats** – Välj den plats där standardförpackningsstationen finns.
    - **Distributionslager** – Välj det distributionslager där standardförpackningsstationen finns.
    - **Plats** – Välj platsen för standardförpackningsstationen.

1. På snabbflikarna **Användare** kan du skapa val mellan flera användarkonton för lagerställeapp för den valda arbetaren. Varje konto associeras med ett specifikt lagerställe eller lagerställen. Använd verktygsfältet om du vill lägga till eller ta bort användarkonton, återställa lösenordet för ett valt konto eller tilldela lagerställen till ett valt konto. Ange följande fält för varje användarkonto:

    - **Användar-ID** – Ange ett unikt ID.
    - **Användarnamn** – Ange ett namn på ID.
    - **Standardlagerställe** – Ställ in standardlagerstället där arbetaren vanligtvis arbetar. Du kan använda verktygsfältet om du vill tilldela ytterligare lagerställen, och arbetaren kan växla mellan lagerställen genom att använda den indirekta aktiviteten för **Ändra lagerställe** på menyobjektet på mobil enhet.
    - **Menynamn** – Välj rotmenyn som ska vara startsidan för arbetaren. Möjligheten att ställa in rotmenyer för varje arbetare är användbart eftersom du kan styra menystrukturen som varje arbetare kan använda. Menyn för arbetare som bara är aktiva i utgående område kan till exempel skräddarsys för uppgifter som är relaterade till utgående operationer för det området.
    - **Inaktiv** – En markerad kryssruta anger att användarkontot är inaktivt. Användarkontot inaktiveras automatiskt om en arbetare anger fel lösenord fem gånger i en rad i lagerställeprogrammet. Du kan dock också markera den här kryssrutan manuellt. Avmarkera kryssrutan om du vill göra användaren aktiv igen.

1. På snabbfliken **Arbeta** ange följande fält:

    - **Tillåt åsidosättning av plockplats** – Ställ in det här alternativet till *Ja*, så att arbetaren kan åsidosätta platsen för plocksteg. Den här kapaciteten kan vara användbar om det fysiska lagret inte matchar den system föreslagna platsen.
    - **Tillåt åsidosättning av placeringsplatsen** – Ställ in det här alternativet till *Ja*, så att arbetaren kan åsidosätta platsen för placeringssteg. Den här kapaciteten kan vara användbar om den föreslagna placeringsplatsen är full eller inte tillgänglig, eller om mellanlagringsplatser har ändrats.
    - **Tillåt försäljning över plockning** – Ange det här alternativet till *Ja*, så att arbetaren kan överplocka när försäljningsorder plockas. För mer information, se [Överplockning för försäljningsorder och överföringsorder](over-picking-for-sales-and-transfer-orders.md).
    - **Tillåt överplockning för överföring** – Ange det här alternativet till *Ja*, så att arbetaren kan överplocka när överföringsorder plockas. För mer information, se [Överplockning för försäljningsorder och överföringsorder](over-picking-for-sales-and-transfer-orders.md).
    - **Tillåt flyttning av lager med associerat arbete** – Ange det här alternativet till *Ja* för att tillåta arbetaren att flytta inventarier som redan är reserverat eller som redan är kopplat till annat arbete. För mer information, se [Lagerrörelse med tillhörande arbete med lagerstyrning](move-inventory-associated-work.md).
    - **Tillåt manuell omfördelning av artiklar** – Ange det här alternativet till *Ja* för att aktivera manuell omallokering för arbetaren vid kort plockning. Artikelomfördelningen leder till att arbetare plockar lager från en annan plats. Även om automatisk omallokering är tillgänglig för alla medarbetare, kräver manuell omplacering explicita inställningar för en arbetare. Möjligheten att kontrollera manuell omfördelning för varje arbetare kan vara användbart eftersom det gör att du kan kontrollera synligheten som varje arbetare har när t.ex. artikelplockning från karantän- eller bulkområdet är begränsat till betrodda medarbetare. Mer information finns i följande blogginlägg: [Automatisk och manuell artikelomfördelning vid kort](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/11/07/automatic-and-manual-item-reallocation-during-the-short-picking-dynamics-365-for-operations-1611/).
    - **Är ansvarig för rullande inventering** – Ställ in det här alternativet till *Ja* för att göra arbetaren till ansvarig för rullande inventering. I det här fallet godkänns alla rullande inventeringar som arbetaren utför på lagerställeappen omedelbart. Fälten **Gräns för högsta procentandel**, **Gräns för högsta kvantitet** och **Gräns för högsta värde** beaktas inte för arbetare som det här alternativet är inställt på *Ja*.
    - **Gräns för högsta procentandel** – Ange den högsta procentgränsen som en rullande inventering kan variera från den förväntade inventeringen utan att kräva godkännande av en ansvarig för rullande inventering.
    - **Gräns för högsta kvantitet** – Ange den totala kvantiteten som den inmatade kvantiteten kan skilja sig från den förväntade kvantiteten (i enheter) utan att kräva godkännande av en cykelräkningsövervakare.
    - **Gräns för högsta värde** – Ange det högsta beloppet som kostnaden för en rullande inventering kan skilja sig från den förväntade kostnaden utan att kräva godkännande av en ansvarig för rullande inventering.

1. Klicka på **Spara** i åtgärdsfönstret.
1. Om du har lagt till ett nytt användarkonto visas dialogrutan **Ange lösenord** visas, där du kan skapa ett enkelt lösenord som användaren kan använda för att logga in på mobilappen. Ange det enkla lösenordet två gånger och välj sedan **Spara lösenord** för att fortsätta.

## <a name="set-the-language-number-formats-and-time-zone-for-each-warehouse-app-user"></a>Ställ in språk, nummerformat och tidszon för varje lagerställe-appanvändare

När en arbetare loggar in på den Warehouse Management-mobilappen ändras språk, nummerformat och tidszoner så att de matchar arbetarnas inställningar. Kontoinställningarna för arbetaren som väljs i steg 3 i avsnittet [Ställ in användarkonton för mobil enhet](#set-wma-users) avgör vilka inställningar som används. Om du behöver separata inställningar för varje användare använder du olika arbetskonton. Följande procedur visar hur du ändrar språk, nummerformat och tidszon för varje lagerställeapp användare.

1. Gå till **Warehouse management \> Inställningar \> Arbetare**.
1. Sök efter namnet på arbetaren som du vill ställa in. Se till att arbetaren har alla nödvändiga användarkonton för lagerställeapp som visas på snabbflikarna **Användare**. Skapa ett nytt användarkonton för arbetare och/eller lägg till lagerställeapp efter behov, genom att följa stegen i avsnittet [Ställ in användarkonton för mobil enhet](#set-wma-users).
1. Gå till **Systemadministration \> Användare \> Användare**.
1. Välj det användarkonto där kolumnen **person** visar namnet på den arbetare som du hittade i steg 2.

    > [!IMPORTANT]
    > Värdena för **Användar-ID** anges på sidan **Användare** är *inte* relaterat till värdet som visas på snabbfliken **Användare** på sidan **Arbetare** som du öppnade i steg 1.

1. I åtgärdsfönstret väljer du **Användaralternativ**.
1. Ange följande fält på fliken **Inställningar**:

    - **Språk** – Välj det språk som arbetaren föredrar. Det här fältet styr även nummerformatet som visas i lagerställeappen.
    - **Datum, tid och nummerformat** – Välj det datum- och tidsformat som arbetaren föredrar. I distributionslagerappen används nummerformatet som associeras med det språk som valts i fältet **Språk** i stället för den här inställningen.
    - **Tidszon** – Välj den tidszon där arbetaren arbetar. Det här fältet påverkar tidstämpeln för alla registreringar som arbetaren gör med hjälp av programmet.

> [!NOTE]
> I vissa fall kan inte lagerställeprogrammet hitta särskilda arbetsinställningar som fastställer språk, nummerformat och tidszon. Följande regler gäller:
>
> - Om programmet inte är anslutet till en Supply Chain Management-miljö (till exempel första gången programmet startas efter installationen) används språket för den lokala enheten. När enhetens språk ändras ändras även appspråket. Mer information om hur du konfigurerar språket för den lokala enheten finns i dokumentationen till din enhet och/eller operativsystem.
> - Om programmet är anslutet till en Supply Chain Management-miljö, men inga inställningar har ställts in för den inloggade arbetaren, väljs språk, nummerformat och tidszon baserat på kontot som är associerat med det klient-ID som enheten använder för att ansluta till Supply Chain Management. För mer information, se [Skapa och konfigurera ett användarkonto i Supply Chain Management](install-configure-warehouse-management-app.md#user-azure-ad).

> [!TIP]
> Om du ser att felaktiga tidstämplar visas för registreringar som görs med hjälp av lagerställeprogrammet kanske du måste justera tidszonen som är inställd för användarkontot som arbetare använder när de loggar in och/eller autentiserar med Supply Chain Management. Som tidigare har nämns kan tidszoninställningen komma från användarkontot som används för att logga in på lagerställeprogrammet, som de ställts in på sidan **Arbetare**. Om användarkontot inte är inställt på sidan **Arbetare** kommer tidszonen från det användarkonto som har associerats med det klient-ID som används för autentisering, enligt inställningar på sidan **[Azure Active Directory appar](install-configure-warehouse-management-app.md)**.
