---
title: Skapa returer i kassan (POS)
description: I detta ämne beskrivs hur du initierar returer för hämtköpstransaktioner eller kundorder i kassaprogrammet för Microsoft Dynamics 365 Commerce (POS).
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.20
ms.openlocfilehash: 496c4fe5230a599acf60fac39e51c43db372f92c
ms.sourcegitcommit: 927574c77f4883d906e5c7bddf0af9b717e492bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129832"
---
# <a name="create-returns-in-pos"></a>Skapa returer i kassan (POS)

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

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

![Sidan Returnerbara produkter](media/returnslist.png)

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

## <a name="additional-resources"></a>Ytterligare resurser

[Returserienummerkontrollerade produkter i kassan (POS)](POS-serial-returns.md)

[Kopplade återbetalningar av tidigare godkända och bekräftade transaktioner](dev-itpro/linked-refunds.md)

[Skapa och uppdatera en retur- och återbetalningspolicy för en kanal](refund_policy_returns.md)

[Visuella konfigurationer för kassaanvändargränssnitt](pos-screen-layouts.md)
