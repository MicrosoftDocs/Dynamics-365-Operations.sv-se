---
title: Ställa in en kundtjänstkanal
description: I det här avsnittet beskrivs hur du skapar en ny kundtjänstkanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b25626dafc07d576699ceba3cc9ca691db45cb9f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997760"
---
# <a name="set-up-a-call-center-channel"></a>Ställa in en kundtjänstkanal


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en ny kundtjänstkanal i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt


I Dynamics 365 Commerce, är kundtjänst en typ av Commerce-kanal som kan definieras i programmet. Om du definierar en kanal för dina kundtjänstenheter kan systemet koppla specifika data och orderbearbetningsstandard till försäljningsorder. Ett företag kan definiera flera kundtjänstkanaler i Commerce, men det är viktigt att tänka på att en enskild användare bara kan länkas till en kundtjänstkanal. 

Innan du skapar en ny kundtjänstkanal måste du kontrollera att du har slutfört [Förutsättningar för att ställa in kanaler](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Skapa och konfigurera en ny kundtjänstkanal

Följ stegen nedan om du vill skapa och konfigurera en ny kundtjänstkanal.

1. I navigeringsfönstret, gå till **Retail och Commerce \> Kanaler \> Kundtjänster \> Alla kundtjänster**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Namn** ange ett namn på den nya kanalen.
1. Välj lämplig **Juridisk enhet** från listrutan.
1. Välj lämplig plats för **Lagerställe** från listrutan. Den här platsen kommer att användas som standard på försäljningsorder som skapas för den här kundtjänstkanalen, såvida inte andra standardvärden har definierats på kund- eller artikelnivå.
1. I fältet **Standardkund** ange en giltig standardkund. Dessa data används för att hjälpa till att automatiskt fylla i standardvärden när nya kundposter skapas. När du skapar kundtjänstorder är det inte tillrådligt att skapa order för standardkunden.
1. I fältet **Meddelandeprofil för e-post** ange en giltig meddelandeprofil för e-post. När order skapas och bearbetas, används e-postprofilen för att utlösa automatiska e-postnotifieringar till kunder med information om deras orderstatus.
1. Ange informationskoden **prisåsidosättning**. Du måste skapa en informationskod för denna första. Den här informations koden anger de orsakskoder som användaren ska uppmanas att välja mellan när funktionen för prisökning används i en kundtjänstorder.
1. Tillhandahåll en informationskod **Spärrkod**. Du måste skapa en informationskod för denna första. Den här informationskoden anger de valfria orsakskoder som användaren ska uppmanas att välja mellan när man spärrar en order.
1. Ange en informationskod **Kredit**. Du måste skapa en informationskod för denna första. Den här informationskoden innehåller en uppsättning orsakskoder som användaren kan välja från när du använder funktionen orderkredit i en kundtjänst för att ge diverse återbetalningar till kunden av kundserviceorsaker.
1. Valfritt: ställ in ekonomiska dimensioner på snabbfliken **ekonomiska dimensioner**. De dimensioner som anges här kommer att visas som standard på alla försäljningsorder som skapas i den här kundtjänstkanalen.
1. Klicka på **Spara**.

Följande bild visar hur en ny kundtjänstkanal skapas.

![Ny kundtjänstkanal](media/channel-setup-callcenter-1.png)

I bilden nedan visas ett exempel på kundtjänstkanal.

![Exempel på kundtjänstkanal](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>Konfiguration av ytterligare kanal

Ytterligare uppgifter som krävs för inställningar av kundtjänstkanal inkluderar inställning av betalsätt och leveranssätt.

I följande bild visas konfigurationsalternativen **leveranssätt** och **betalsätt** på fliken **inställning**.

![Ytterligare åtgärder för konfigurering av kundtjänstkanal](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a>Ange betalsätt

Om du vill ställa in betalsätt följer du dessa steg för varje betalningstyp som stöds på den här kanalen. Användarna måste välja bland fördefinierade betalsätt för att kunna länka dem till kundtjänstkanalen. Innan du ställer in dina betalsätt för kundtjänst, ställ först in dina betalsätt i **Retail och Commerce \> Kanalinställning \> Betalsätt \> Betalsätt**.

1. I åtgärdsfönstret, välj fliken **Inställningar** och välj sedan **betalningssätt**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I navigeringsfönstret väljer du ett betalsätt från tillgängliga fördefinierade betalningar.
1. Konfigurera eventuella ytterligare inställningar efter behov för betalningstypen. För kreditkort, presentkort eller förmånskort behöver du ytterligare inställningar genom att välja funktionen **kortinställningar**. 
1. Konfigurera lämpliga bokföringskonton för betalningstypen avsnittet **bokföring**.
1. I åtgärdsfönstret, klicka på **spara**.

I bilden nedan visas ett exempel på en kontantbetalningsmetod.

![Exempel på betalsätt](media/channel-setup-callcenter-payments.png)

### <a name="set-up-modes-of-delivery"></a>Ställ in leveranssätt

Du kan visa de konfigurerade leveranssätten genom att välja **Leveranssätt** från fliken **Inställningar** i **Åtgärdsfönstret**.  

Om du vill ändra eller lägga till ett leveranssätt som ska associeras till den här kundtjänstkanalen följer du stegen nedan.

1. I formuläret kundtjänstlägen för leveranssätt väljer du **Hantera leveranssätt**
1. I åtgärdsfönstret, välj **Ny** om du vill skapa ett nytt leverans sätt, eller välj ett befintligt läge.
1. I avsnittet **butikskanaler**, klicka på **lägg till rad** om du vill lägga till kundtjänstkanalen. Lägga till kanaler med hjälp av organisationsnoder istället för att lägga till varje kanal individuellt kan lägga till kanaler effektivare.
1. Se till att leveranssättet har konfigurerats med data på snabbfliken **produkter** och på snabbfliken **adresser**. Om inga produkter eller leveransadresser är giltiga för leveranssättet, orsakar fel när du väljer det under orderregistrering.
1. När du har ändrat i konfiguration av kundtjänsts leveranssätt måste jobbet **bearbeta leveranssätt** köras för att ändra matrisen. Det här jobbet hittar du genom att navigera till **Retail och Commerce \> Retail och Commerce IT \> Bearbeta leveranssätt**.

I bilden nedan visas ett exempel på ett leveranssätt.

![Ställ in leveranssätt](media/channel-setup-retail-7.png)

### <a name="set-up-channel-users"></a>Ställ in en kanalanvändare

Om du vill skapa en försäljningsorder som är länkad till en kundtjänstkanal från Commerce-administration måste användaren som skapar försäljningsordern vara kopplad till kundtjänstkanalen. Användaren kan inte manuellt länka en försäljningsorder som har skapats i Commerce-administration till kundtjänstkanalen. Länken är systematisk och baseras på användaren och användarens relation till kundtjänstkanalen. En användare kan bara länkas till en kundtjänstkanal.

1. I åtgärdsfönstret, välj fliken **Kanal** och välj sedan **Kanalanvändare**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Välj ett befintligt **användar-ID** från listrutan urvalslista för att koppla användaren till kundtjänstkanalen

När kanalanvändarinställningen är klar och användaren skapar en ny försäljningsorder i Commerce-administration kommer försäljningsorder att kopplas till deras tillhörande kundtjänstkanal. Alla konfigurationer för den här kanalen kommer att tillämpas systematiskt på försäljningsordern. En användare kan bekräfta vilken kundtjänstkanal som försäljningsordern är kopplad till genom att visa kanalnamnreferensen i försäljningsorderrubriken.


### <a name="set-up-price-groups"></a>Ställa in prisgrupper

Prisgrupper är valfria, men om de används kan du kontrollera vilka försäljningspriser som ska erbjudas till kunder som ställer order i den här kundtjänstkanalen. Om en prisgrupp inte har konfigurerats för kunden, eller om katalogprisgrupper inte används på försäljningsordern (med hjälp av fältet **Källkod-ID** i orderrubriken för kundtjänst), används kanalprisgruppen för att hitta artikelpriserna. Om en prisgrupp inte finns på kundtjänstkanalen används standardartikelns huvudpriser. 

Om du vill ställa in en prisgrupp gör du följande.

1. I åtgärdsfönstret, välj fliken **Kanal** och välj sedan **Prisgrupper**.
1. Klicka på **Nytt** i Åtgärdsfönstret.
1. Välj en **butiksprisgrupp** i listrutans urvalslista.

## <a name="additional-resources"></a>Ytterligare resurser

[Förutsättningar för kanalinställningar](channels-prerequisites.md)

[Försäljningsfunktioner för kundtjänst](call-center-functionality.md)

[Ställ in alternativ för orderbearbetning för kundtjänst](set-up-order-processing-options.md)

[Kundtjänstkataloger](call-center-catalogs.md)

[Ställa in och arbeta med bedrägerivarningar](set-up-fraud-alerts.md)

[Ställa in kontinuitetsprogram för kundtjänster](set-up-continuity-program.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]