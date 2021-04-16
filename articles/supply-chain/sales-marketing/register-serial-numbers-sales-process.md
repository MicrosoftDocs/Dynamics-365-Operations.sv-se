---
title: Arbeta med serialiserade artiklar
description: Det här ämnet beskriver hur du kan registrera serienummer på följesedlar eller fakturor under försäljningsprocessen. Den här funktionen är användbar om ett företag vill hämta in serienummer för service- och garantiändamål men inte måste underhålla serienummer i lager från inleverans till utleverans.
author: omulvad
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResTrackingDimensionGroup, InventTrackingRegisterTrans, SalesEditLines, SalesTable, InventSerial
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28931
ms.assetid: 5d39630f-607e-492b-8c1e-790ca53effa0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d423c1ab992c0c83c7e7fc14c7bba424048d396
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839063"
---
# <a name="working-with-serialized-items"></a>Arbeta med serialiserade artiklar

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver hur du kan registrera serienummer på följesedlar eller fakturor under försäljningsprocessen. Den här funktionen är användbar om ett företag vill hämta in serienummer för service- och garantiändamål men inte måste underhålla serienummer i lager från inleverans till utleverans.

Många företag vill bara hämta in serienummer för uppfylla tjänste- och garantikrav och måste inte underhålla serienummer i lager från inleverans till utleverans. I dessa situationer kan låta dig registrera serienumren på följesedlar eller fakturor när produkter säljs. Om produkter lämnas tillbaka senare kan du spåra varje produkt till en faktura för att avgöra om du har sålt produkten, och om service- eller garantiskyldigheterna gäller.

Du måste aktivera serienummer för försäljningsprocessen med alternativet **Aktiv i försäljningsprocess** på sidan **Spårningsdimensionsgrupper**. Följande händelser inträffar i Supply Chain Management:
-   På snabbfliken **Serienummer** markeras alternativet **Serienummerkontroll**. Om det här alternativet är markerat, måste du registrera ett serienummer för varje artikel på följesedeln eller fakturan.
-   Alla val i spårningsdimensionsgruppen för serienummer är avmarkerade, utom alternativet **Tom utleverans tillåten**. Du kan markera alternativet **Tom utleverans tillåten** om du vill åsidosätta serienummerkontrollen och tillåta produkter och packas faktureras, utan att registrera serienummer.

## <a name="when-do-i-register-serial-numbers-during-the-sales-process"></a>När registrerar jag serienummer under en försäljningsprocess?
Du kan registrera serienummer på följesedeln för en försäljningsorder på fakturan. När du förbereder en faktura för en seriekopplad artikel som har skickats med en följesedel, kan du välja vilket serienummer på följesedeln som ska faktureras. Antalet registrerade serienummer får inte överstiga den levererade artikelkvantiteten. Om du skapar en delvis faktura kan du välja färre seriekopplade artiklar än vad som registrerades på följesedeln. När du skriver ut en följesedel eller en faktura, inkluderas serienumren som har registrerats.

## <a name="can-i-enter-serial-numbers-by-scanning-them-or-do-i-have-to-type-them"></a>Kan jag ange serienummer genom att skanna dem, eller måste jag skriva in dem?
Du kan antingen skanna eller ange serienummer. Om du använder skanner, avgör skanningsläget om du vill lägga till eller ta bort serienummer i listan över serienummer på fakturan eller följesedeln. Om du vill skanna efter serienummer, till exempel genom att använda en handhållen streckkodsskanner, konfigurera skannern för att skicka ett Enter- eller TABB-kommando efter serienumret. Detta kommando indikerar slutet av dataströmmen. Annars måste du trycka på Retur eller TABB på tangentbordet efter att du har skannat varje serienummer.

## <a name="if-i-enable-serial-numbers-for-the-sales-process-do-i-have-to-register-all-serial-numbers-for-all-items"></a>Om jag aktiverar serienummer för försäljningsprocessen, behöver jag registrera alla serienummer för alla artiklar?
Inställningarna för den spårningsdimensionsgrupp som har tilldelats produkten bestämmer om serienummer måste registreras för alla artiklar på en följesedel eller en faktura. När du aktiverar serienummer för en försäljningsprocess, markeras alternativet **Serienummerkontroll** automatiskt. Det innebär att du måste registrera ett serienummer, eller en blankregistrering, för ett oläsligt nummer för varje artikel på följesedeln eller fakturan. Om du inte vill kräva ett serienummer för varje artikel, markerar du alternativet **Tom utleverans tillåten** på den spårningsdimensiongrupp som är tilldelad artikeln. Du kan sedan registrera färre serienummer än den kvantitet av artiklarna som har skickats. Om du registrerar fler serienummer än den kvantitet artiklar som skickas, kan du inte bokföra följesedeln eller fakturan.

## <a name="can-i-register-serial-numbers-for-partial-invoices-and-partial-shipments"></a>Kan jag registrera serienummer för delfakturor och delleveranser?
Du kan skapa delvisa fakturor och följesedlar för försäljningsorder och register endast serienumren för de artiklar som dessa fakturor och följesedlar innehåller. Om du vill skapa en delfaktura, och du har mer än en följesedel för försäljningsordern, kan du inkludera serienummer från mer än en följesedel. Det kan dock bara finnas en följesedel där alla serienummer inte är inkluderade. Om du till exempel har tre följesedlar och varje innehåller två seriekopplade artiklar, kan du inte skapa en delfaktura för en artikel från varje följesedel.

## <a name="what-do-i-do-when-a-serial-number-isnt-readable"></a>Vad gör jag när ett serienummer inte är läsligt?
Om ett serienummer inte kan läsas eller skannas kan du skapa en tom rad för artikeln genom att klicka på **Det går inte att läsa** på sidan **Serienummer**. Om serienumret blir tillgängligt senare kan du uppdatera fakturan eller följesedeln. Mer information finns i nästa avsnittet ”Kan jag korrigera eller ändra serienummer som jag har registrerat för en försäljningsorder?”.

## <a name="can-i-correct-or-change-the-serial-numbers-that-i-have-registered-for-a-sales-order"></a>Kan jag korrigera eller ändra serienummer som jag har registrerat för en försäljningsorder?
Ja du kan korrigera serienummer, när följande villkor uppfylls:
-   **Fakturor** – Du kan ändra serienummer för de artiklar som du ännu inte har fakturerat. Följesedeln uppdateras då också. Men om en försäljningsorderrad korrigerades genom att registrera en negativ kvantitet kan du inte ändra serienummer för försäljningsorderraden.
-   **Följesedlar** - Du kan inte delvis korrigera en följesedelrad som innehåller seriekopplade artiklar. Du måste återföra hela kvantiteten för raden. Om en följesedel har annullerats eller åtgärdats behöver du inte registrera de återförda serienumren igen när du skapar en ny följesedel för samma seriekopplade artiklar. Numren som har registrerats kommer att användas.

## <a name="can-i-view-the-serial-numbers-that-were-shipped-together-with-a-specific-packing-slip-or-that-were-included-on-an-invoice"></a>Kan där jag visa serienumren som har skickats med en viss följesedel, eller som har inkluderats i en faktura?
Ja kan du köra en fråga på följesedeljournalraden, eller fakturajournalraden som visar serienummer i en lista, som inkluderade, där alla i dokumentet.

## <a name="can-i-view-the-serialized-items-that-i-have-on-hand"></a>Kan jag visa de seriekopplade artiklar som jag har i lager?
Nej, du kan inte visa de serialiserade artiklarna som du har i lager, eftersom serienummer inte registrerats för artiklar förrän artiklarna säljs.

## <a name="can-i-register-serial-numbers-for-catchweight-items"></a>Kan jag registrera serienummer för fångstviktartiklar?
Nej, under en försäljningsprocess kan du inte registrera serienummer för fångstviktartiklar. Dessutom, om en produkt har ställts in som en fångstviktartikel, kan du inte tilldela produkten till en spårningsdimensionsgrupp som är inställd på att endast använda serienummer under försäljningsprocessen.

## <a name="can-i-register-serial-numbers-at-the-retail-pos"></a>Kan jag registrera serienummer i Kassa?

Ja, kassan kommer att uppmana användaren att ange ett serienummer, där användaren säljer en artikel som har tilldelats en spårningsdimensionsgrupp som har ställts in för att endast använda serienummer under försäljningsprocessen.

## <a name="what-security-roles-are-required-in-order-to-register-serial-numbers-during-the-sales-process"></a>Vilka säkerhetsroller krävs för att registrera serienummer under försäljningsprocessen?
Den här funktionen är tillgänglig för alla roller som kan underhålla försäljningsföljesedlar och försäljningsfakturor. Följande behörigheter gör det möjligt för anställda att korrigera serienummer och registrera blanka poster för serienummer som inte kan läsas eller skannas:
-   Underhåll korrigering av serienummer
-   Underhåll registrering av oläsliga serienummer







[!INCLUDE[footer-include](../../includes/footer-banner.md)]