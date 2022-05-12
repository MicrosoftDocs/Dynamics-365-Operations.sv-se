---
title: Skapa returer i kassan (POS)
description: I detta ämne beskrivs hur du initierar returer för hämtköpstransaktioner eller kundorder i kassaprogrammet för Microsoft Dynamics 365 Commerce (POS).
author: hhainesms
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.20
ms.openlocfilehash: c8e06c0d83e3bc2f5efea1e3a8124c700706aa2e
ms.sourcegitcommit: 9e1129d30fc4491b82942a3243e6d580f3af0a29
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8648998"
---
# <a name="create-returns-in-pos"></a>Skapa returer i kassan (POS)

[!include [banner](includes/banner.md)]

I detta ämne beskrivs hur du initierar returer för hämtköpstransaktioner eller kundorder i kassaappen för Microsoft Dynamics 365 Commerce (POS).

> [!NOTE]
> I Commerce-versionen 10.0.20 och senare finns en ny funktion kallad **Enhetlig returbearbetningserfarenhet i kassan**. Denna funktion ger en mer konsekvent och enhetlig returprocess i kassan, oavsett transaktionstyp (hämtköpstransaktion eller kundorder) eller den ursprungliga kanal som ordern skapades i. Vi rekommenderar att alla organisationer aktiverar denna nya funktion för att förbättra den generella tillförlitligheten hos returbearbetningen via POS.
>
> När funktionen har aktiverats kan den inte stängas av.

## <a name="process-returns-by-using-the-return-transaction-operation"></a>Bearbeta returer med hjälp av returtransaktionsfunktionen

Vi rekommenderar att du lägger till returtransaktionsfunktionen i din [kassaskärmlayout](pos-screen-layouts.md). I versioner före Commerce-version 10.0.20 stöder funktionen för returtransaktion korrekt bearbetning endast för returer av hämtköpstransaktioner. När du aktiverar funktionen **Bearbetningsupplevelse för enhetliga returer i kassan** i Commerc-version 10.0.20 eller senare stöder funktionen för returtransaktion även bearbetning av returer med ursprung i kundorder, exempelvis order för "avhämtning" eller "leverera till husdörren" som redan fakturerats.

Via returtransaktionsfunktionen kan användarna söka efter en hämtköpstransaktion eller en kundorder som ska returneras genom att ange något av följande fyra sökvillkor: Användarna kan ange dessa kriterier genom att använda ett tangentbord, ett tangentbord på skärmen eller en streckkodsskanner.

- Kvitto-ID
- Ordernummer
- Kanalreferens-ID (även kallat orderbekräftelse-ID)
- Faktura-ID

Om en transaktion eller order hittas som matchar sökkriterierna visas sidan **Returnerbara produkter**. Där kan användarna ange vilka artiklar som returneras. De kan också ange returkvantiteter och orsakskoder.

För varje orderrad i listan med returnerbara varor visar kassan (POS) information om den ursprungliga inköpskvantiteten och kvantiteterna från eventuella returer som tidigare bearbetats. Returkvantiteten som en användare anger för en orderrad måste vara mindre än eller lika med värdet i fältet **Tillgängliga för retur**.

![Sidan Returnerbara produkter.](media/returnslist.png)

Om en användare har den fysiska produkten och den produkten har en streckkod kan användaren skanna streckkoden för att registrera returen i samband med retur. Varje skanning av streckkoden ökar returkvantiteten med en (1) artikel. Om streckkodsetiketten emellertid har en inbäddad kvantitet anges den kvantiteten i fältet **Returneras nu**.

Användarna kan också manuellt välja vilka artiklar som ska returneras på sidan **Returnerbara produkter** och sedan uppdatera fältet **Returneras nu** genom att använda informationsfönstret till höger.

Om den maximala tillgängliga kvantiteten för **Returneras nu** anges för en transaktion kan användaren välja funktionen **Markera alla** i kassaappens fält i syfte att ange högsta möjliga returkvantitet på samtliga rader.

För varje rad som har en **Returneras nu**-kvantitet måste användaren välja en returorsakskod i informationsrutan. För returer av hämtköpstransaktioner konfigureras returorsakskoderna som infokoder i butikens funktionsprofil. För returer av kundorder konfigureras returorsakskoderna på sidan **Returorsakskoder** i Dynamics 365 Commerce-administrationen.

När returkvantiteten och orsakskoden har ställts in för varje artikel som måste returneras kan användaren välja funktionen **Retur** i kassaappens fält i syfte att fortsätta med bearbetningen. Sidan för kassatransaktion visas, där de returnerbara artiklarna som markerades på föregående sida har lagts till i kundvagnen. Kvantiteterna **Returneras nu** för artiklarna visas som rader med negativ kvantitet i transaktionen, och den totala återbetalningen beräknas.

Användare kan lägga till rader i en returtransaktion om de skapar en kursorder. Användarna kan också lägga till fler ad-hoc-returartiklar i en returtransaktion genom att använda funktionen **Returprodukt** för en vald försäljningsrad med positiv kvantitet som har lagts till.

> [!NOTE]
> Funktionen **Returprodukt** i kassan (POS) validerar inte mot någon ursprunglig transaktion och gör det möjligt att returnera valfri produkt. Vi rekommenderar därför att endast behöriga användare tillåts utföra den här åtgärden eller att en åsidosättning utförd av chef krävs om den här åtgärden används.

Om en återbetalning förfaller i kassan kan organisationer konfigurera [policyer för återbetalning](refund_policy_returns.md) som begränsar de betalningsmetoder som kan användas för att utföra återbetalningar till kunder. Om den ursprungliga transaktionen har betalats med kreditkort kan användarna, beroende på betalningsföretag och systemkonfiguration, ha möjlighet att [utfärda en återbetalning till det ursprungliga kortet](dev-itpro/linked-refunds.md). I så fall kan återbetalningen behandlas utan att kunden måste dra sitt kreditkort igen. Den ursprungliga betalningstoken används för att utfärda återbetalningen.

## <a name="other-return-options-in-pos"></a>Andra returalternativ i kassan (POS)

När funktionen **Enhetlig returbearbetningserfarenhet i kassan** aktiveras kan kunderna också använda funktionen **Visa journal** i kassan (POS) för att initiera en retur för en hämtköptransaktion eller en kundorder. De kan sedan välja en transaktion i journalen och därefter välja funktionen **Retur** i fältet för kassaappen (POS). Denna operation är endast tillgänglig om det finns returnerbara rader på ordern. Den initierar samma användarupplevelse som funktionen **Returnera transaktion**.

Användare kan också använda funktionen **Återkalla order** i kassan för att söka efter och återkalla kundorder. (Denna funktion kan inte användas för hämtköptransaktioner). När en kundorder har valts kommer i detta fall funktionen **Retur** i fältet för kassaappen (POS) användas för att initiera en retur för kundordern. Denna operation är endast tillgänglig om det finns returnerbara rader på ordern. Den initierar samma användarupplevelse som funktionen **Returtransaktion** eller **Visa journal**.

## <a name="return-orders-are-posted-to-commerce-headquarters-as-sales-orders"></a>Returorder bokförs i Commercea-dministrationen som försäljningsorder 

När funktionen **Enhetlig returbearbetningserfarenhet i kassan (POS)** är aktiverat kommer samtliga returer som skapas i kassan (POS) att skrivas i Commerce-administrationen som säljorder med negativa rader. I versioner före Commerce version 10.0.20 kan användarna välja om returorder ska bokföras som försäljningsorder som har negativa rader eller om de ska vara returorder som skapas via auktoriseringsprocessen för varuretur (Return Merchandise Authorization, RMA). 

I funktionen **Enhetlig returbearbetningserfarenhet i kassan (POS)** har funktionen för att använda RMA-processen för att skapa returer i POS avskrivits.. När denna funktion har aktiverats skapas alla returer som försäljningsorder med negativa rader.

## <a name="offline-return-processing-improvements"></a>Förbättringar av returbearbetning offline

När en retur bearbetas i kassan (POS) gör systemet i de flesta fall ett försök att ringa ett tjänsteanrop i realtid (RTS) till Commerce-administrationen i syfte att validera de aktuella kvantiteter som är tillgängliga för retur. Med den här valideringen kan du förhindra bedrägeriscenarier där en kund försöker returnera samma artikel på flera platser.

För att hantera situationer där RTS-anropet inte kan göras på grund av nätverks- eller anslutningsproblem har en process implementerats med syfte att regelbundet synkronisera returkvantitetsdata från Commerce-administrationen till en butiks kanaldatabas. Denna returspårning på kanalsidan gör det lättare att se till att de **Tillgängliga för retur**-kvantiteter som visas i kassan (POS) är relativt korrekta, även då kassan (POS) är offline. Det garanterar också att kassan (POS) kan fortsätta att validera informationen på kanalsidan i syfte att förhindra felaktiga returer.

Om du vill använda offline-returprocessen på rätt sätt ska organisationer schemalägga batchjobbet **Uppdatera returkvantiteter** i Commerce-administrationen så att detta körs regelbundet. Vi rekommenderar att det här jobbet körs på samma frekvens som P-jobbet som hämtar nya transaktioner från Commerce-kanaler till Commerce-administrationen.

Jobbet **Uppdatera returkvantiteter** beräknar den kvantitet som är tillgänglig för retur för alla försäljningsorder som finns i Commerce-administrationen. De data som beräknas i jobbet måste sedan skickas till kanaldatabaser så att butikskanalerna kan uppdateras. Distributionsjobbet **Returkvantiteter** (1200) används i detta syfte. Eftersom data som rör den returbara kvantiteten synkroniseras från Commerce-administrationen kan kassan (POS) - om en retur bearbetas i POS, men RTS-anropet inte kan göras - använda returinformationen på kanalsidan för att validera de kvantiteter som är **Tillgängliga för retur** för en given försäljningsrad.

När RTS-anrop inte kan göras och kassan (POS) använder data på kanalsidan för returvalidering, informerar ett varningsmeddelande användarna om att de skapar en "offline-retur". De är därför medvetna om att den **Tillgängliga för retur**-kvantitet som anges i kassan (POS) kan vara inaktuell och felaktig, beroende på när jobbet **Uppdatera returkvantiteter** senast bearbetades och synkroniserades med kanalen.

En kund bearbetade exempelvis nyligen en retur för en orderrad i en annan kanal, men denna data har ännu inte synkroniserats med kanaldatabaserna via jobbet **Uppdatera returkvantiteter**. Kunden går sedan till en annan butik och försöker returnera samma artikel på nytt. Om butiken i detta fall inte kan utföra RTS-anropet till Commerce-administrationen för att hämta returdata i realtid, tillåter kassan (POS) att artikeln returneras på nytt. Användaren varnas dock för att informationen som används för att validera returen kan vara inaktuell. Meddelandet som användaren får är bara ett varningsmeddelande. Detta hindrar inte användaren från att fortsätta bearbeta returen.

Om kanalsidans information av någon anledning inte är uppdaterad och en offlineretur bearbetas för en kvantitet som överskrider den faktiska kvantiteten för **Tillgänglig att returnera**, kan ett fel komma att genereras när utdragsbokföringen körs för att skapa transaktionen i Commerce-administrationen.

> [!NOTE]
> När funktionen **Enhetlig returbearbetningserfarenhet i kassan (POS)** är aktiverad blir nya tillvalsfunktioner tillgängliga som stöder bekräftandet av serialiserade produktreturer. Mer information finns i [Returserienummerkontrollerade produkter i kassan (POS)](POS-serial-returns.md).

## <a name="version-details"></a>Versionsdetaljer

Följande lista innehåller minimiversionskraven för olika komponenter.
- Commerce-administration: Version 10.0.20
- Commerce Scale Unit (CSU): Version 9.30
- Kassa (POS): Version 9.30

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>Aktivera korrekt momsberäkning för returer med delkvantitet

Med hjälp av den här funktionen kan du se till att momsen blir lika med det momsbelopp som ursprungligen debiterades när en order returneras med hjälp av flera fakturor.

1. Gå till arbetsytan **Funktionshantering** och sök efter **Aktivera korrekt momsberäkning för returer med delkvantitet**.
1. Välj funktionen **Aktivera korrekt momsberäkning för returer med delkvantitet** och välj sedan **Aktivera**.

## <a name="set-up-return-locations-for-retail-stores"></a>Ställa in returplatser för butiker

Handel låter dig ställa in returplatser baserat på butiksinfokoder och orsakskoder för försäljning och marknadsföring. När kunder returnerar köp anger kassapersonal ofta orsaken till returen. Du kan ange att returnerade produkter ska tilldelas olika returställen i lagret, baserat på infokoder och orsakskoder som kassapersonal väljer i kassaregistret.

En kund returnerar till exempel en defekt produkt, och kassören bearbetar returtransaktionen. När Retail POS visar infokoden för returer väljer kassören delkoden för defekta returer. Den returnerade produkten tilldelas sedan automatiskt till en viss returplats.

En returplats kan vara ett lagerställe, en plats på ett lagerställe eller en även specifik lastpall, beroende på vilka lagerplatser organisationen har ställt in. Du kan mappa varje returplats till en eller flera detaljinformationskoder och orsakskoder för försäljning och marknadsföring.

### <a name="prerequisites"></a>Förutsättningar

Innan du kan ställa in returplatser måste du ställa in följande element:

- **Butiksinfokoder** - promptar i kassan som har ställts in i modulen **Butik**. Mer information finns i [Ställa in informationskoder](/dynamicsax-2012/appuser-itpro/setting-up-info-codes).
- **Orsakskoder för försäljning och marknadsföring** – promptar i kassan som har ställts in i modulen **Försäljning och marknadsföring**. Mer information finns i [Ställa in orsakskoder](/dynamicsax-2012/appuser-itpro/set-up-return-reason-codes).
- **Lagerplatser** – Platserna där lager hålls. Mer information finns i [Konfigurera lagerplatser](/dynamicsax-2012/appuser-itpro/about-locations).
    
### <a name="set-up-return-locations"></a>Ställ in returplatser

Så här ställer du in returplatser.

1. Gå till **Butik och handel \> Kanalinställning \> Lagerställen** och välj ett lagerställe.
1. På snabbfliken **Butik** på fältet **Standardreturplats** väljer du lagerplatsen som ska användas för returer där informationskoder eller orsakskoder inte är mappade till returplatser.
1. I fältet **Standardlastpall för returer** väljer du den pall som ska användas för returer där informationskoder eller orsakskoder inte är mappade till returplatser.
1. Gå till **Butik och handel \> Lagerhantering \> Returplatser**.
1. Välj **Ny** om du vill skapa en returplatspolicy.
1. Ange ett unikt namn och en beskrivning för returplatsen.

    > [!NOTE]
    > Namnet anges automatiskt om en nummerserie har ställts in för returplatser.

1. På snabbfliken **Allmänt** ange alternativet **Skriv ut etiketter** till **Ja** för att skriva ut etiketter för alla produkter som är tilldelade returställen.
1. Ange alternativet **Blockera lager** till **Ja** för att ta returnerade produkter på den förinställda returplatsen ur lagret och förhindra att de säljs.
1. Mappa specifika butiksinfokoder och delkoder för returplatser genom att följa dessa steg:

    1. På snabbfliken **Butiksinfokoder** väljer du **Lägg till**.
    1. I fältet **Informationskod** väljer du en informationskod för returer.
    1. Välj en **delkod** för orsaken till returen i fältet . Fältet **Beskrivning** visar beskrivningen av den valda delkoden.
    1. I fältet **Butik** väljer du den butik där informationskoden används.
    1. Använd fälten **Lagerställe**, **Plats** och **Lastpalls-ID** för att ange en returplats. Till exempel, för att ange en plats i en butik, välj en butik i **Butik** och plats i fältet **Plats**.
    1. Markera kryssrutan **Spärra lager** om du vill ta bort returnerade produkter ur lagret och förhindra att de säljs.

1. Mappa specifika orsakskoder för försäljning och marknadsföring för returplatser genom att följa dessa steg:

    1. På snabbfliken **Orsakskoder för försäljning och marknadsföring** väljer du **Lägg till**.
    1. I fältet **Orsakskod** välj en orsakskod för returer. Fältet **Beskrivning** visar beskrivningen av den valda orsakskoden.
    1. I fältet **Butik** väljer du den butik där orsakskoden används.
    1. Använd fälten **Lagerställe**, **Plats** och **Lastpalls-ID** för att ange en returplats. Om du till exempel vill välja en viss lastpall på ett lagerställe väljer du ett lagerställe i fältet **lagerställe**, en plats i fältet **Plats** och en lastpall i fältet **lastpall-ID**.
    1. Markera kryssrutan **Spärra lager** om du vill ta bort returnerade produkter ur lagret och förhindra att de säljs.

    > [!NOTE]
    > Om en returadresspolicy används för en vara, men returorsaken som en kassörska väljer inte matchar någon kod som anges på snabbfliken **Butiksinfokoder** eller **Orsakskoder för försäljning och marknadsföring** skickas varan till den förinställda returplatsen som är definierad på sidan **Lagerställe**. Inställningen av kryssrutan **Spärra lager** på snabbfliken **Allmänt** på sidan **Returplatser** avgör om den returnerade artikeln ska vara lagerspärrad.

1. Gå till **Butik och handel \> Handelsprodukthierarki**.
1. På snabbfliken **Hantera kategoriegenskaper för lager** i fältet **Returplats** välj returplats. Eftersom flera principer för en returplats kan definieras för samma butik, bestämmer värdet som du väljer här vilken returplatspolicy som används.

## <a name="additional-resources"></a>Ytterligare resurser

[Returserienummerkontrollerade produkter i kassan (POS)](POS-serial-returns.md)

[Kopplade återbetalningar av tidigare godkända och bekräftade transaktioner](dev-itpro/linked-refunds.md)

[Skapa och uppdatera en retur- och återbetalningspolicy för en kanal](refund_policy_returns.md)

[Visuella konfigurationer för kassaanvändargränssnitt](pos-screen-layouts.md)
