---
title: "Använda sökningar för att söka efter information"
description: "I Microsoft Dynamics 365 for Finance and Operations har många fält sökningar som hjälper dig att enkelt hitta rätt eller önskat värde. Flera förbättringar har lagts till sökningar för att göra dessa kontroller mer användbara och göra användarna mer produktiva. I det här avsnittet lär du dig om dessa nya sökningsfunktionerna och du får några användbara tips för att få optimal användning av sökningar i systemet."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 76f4fa558dca2964d898975f004ebdccdee5e998
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="use-lookups-to-find-information"></a>Använda sökningar för att söka efter information

[!include[banner](../includes/banner.md)]


I Microsoft Dynamics 365 for Finance and Operations har många fält sökningar som hjälper dig att enkelt hitta rätt eller önskat värde. Flera förbättringar har lagts till sökningar för att göra dessa kontroller mer användbara och göra användarna mer produktiva. I det här avsnittet lär du dig om dessa nya sökningsfunktionerna och du får några användbara tips för att få optimal användning av sökningar i systemet.  

<a name="responsive-lookups"></a>Responsiv sökning
------------------

I tidigare versioner av Finance and Operations, när du kommunicerar med en sökkontroll, var användaren tvungen att vidta en explicit åtgärd för att öppna den nedrullningsbara menyn. Detta kan ha uppstått genom att skriva en asterisk (\*) i kontrollen för att filtrera sökningen baserat på det aktuella värdet för kontrollen eller genom att använda kortkommandot **Alt**+**nedpil**. Sökningskontroller har ändrats så att de bättre överensstämmer med gällande praxis för webbplatsen:

-   De nedrullningsbara menyerna för sökning ska nu öppnas automatiskt efter en liten paus i skrivandet med det nedrullningsbara menyinnehållet filtrerat efter sökningkontrollens värde.
    -   Observera att den gamla funktionen hos den nedrullningsbara listan som automatiskt öppnas när du har skrivit en asterisk (\*) har ersatts.
-   När den nedrullningsbara menyn för sökning har öppnat sker följande:
    -   Markören sitter kvar i sökningskontrollen (i stället för att fokus flyttas till den nedrullningsbara menyn) så att du kan fortsätta att göra ändringar i kontrollens värde. Användaren kan dock fortfarande använda **UPPIL** och **NEDPIL** för att ändra raderna i den nedrullningsbara menyn och för att ange om du vill markera hela raden på den nedrullningsbara menyn.
    -   Innehållet i den nedrullningsbara menyn justeras efter att ändringar görs i sökningkontrollens värde.

Tänk dig exempelvis ett sökfält som kallas **Ort**. 

Om fokus är i fältet **Ort** kan du börja leta efter orten genom att skriva ett par bokstäver som "kol".  Efter du slutat skriva öppnas sökningen automatiskt, filtrerad på de orter som börjar med "kol". 

[![typeaheadLookupExample](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png) 

Nu är markören kvar i sökfältet. Om du fortsätter att skriva så att värdet är "kolumn" justeras sökinnehållet automatiskt så att det avspeglar det senaste värdet i kontrollen. 

![updateFilterLookupExample](./media/updatefilterlookupexample.png) 

Även om fokus fortfarande är i sökningskontrollen, kan du också använda knapparna **UPPIL** eller **NEDPIL** för att markera den rad som du vill välja. Om du trycker på **Retur** väljs den markerade raden från sökningen och kontrollens värde uppdateras. 

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>Skriva i mer än ett ID-nummer
När du anger data är det naturligt för en användare att försöka identifiera en enhet, till exempel en kund eller leverantör med avseende på namnet i stället för en identifierare som representerar enheten. I den aktuella versionen av Finance and Operations är många (men inte alla) tillåter sökningar nu sammanhangsberoende datainmatning. Denna kraftfulla funktion låter användaren ange ID-numret eller det motsvarande namnet i sökningskontrollen. 

Beakta till exempel fältet **Kundkonto** när du skapar en försäljningsorder. Det här fältet visar den **Konto-ID** för kunden, men en användare skulle normalt föredra att ange **kontonamn** i stället för ett **konto-ID** för det här fältet när de skapar en försäljningsorder, som till exempel " Forest Wholesales" istället för "US-003".

Om användaren har börjat att ange ett **konto-ID** i sökningskontrollen kommer den nedrullningsbara menyn att öppnas automatiskt enligt beskrivningen i föregående avsnitt så att användaren ser sökningen enligt nedan.

[![Sammanhangsbaserad sökning när ett kundkonto-ID har angetts](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)

Användaren kan emellertid också ange början på ett **kontonamn**. Om detta inträffar kommer användaren att se följande sökning. Observera hur kolumnen **Namn** flyttas till den första kolumnen i sökningen och hur sökningen sorteras och filtreras utifrån kolumnen **Namn**.

[![Sammanhangsbaserad sökning när ett kundnamn har angetts](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>Med hjälp av rutnätets kolumnrubriker för mer avancerad filtrering och sortering
Sökningsförbättringarna som beskrivs i de föregående punkterna förbättrar avsevärt användarnas möjlighet att navigera raderna i en sökning baserat på en "börjar med"-sökning i fältet **ID** eller **Namn**. Det finns dock situationer då mer avancerad filtrering (eller sortering) behövs för att hitta rätt rad. I sådana fall måste användaren använda alternativen för filtrering och sortering i rutnätets kolumnrubriker i sökningen. Anta exempelvis att en medarbetare registrerar en försäljningsorderrad som behöver hitta rätt "kabel" som produkt. Att skriva "kabel" i kontrollen **artikelnummer** hjälper inte eftersom det inte finns några produktnamn som börjar med "kabel". 

![emptyitemlookup](./media/emptyitemlookup.png) 

Användaren måste istället radera värdet i sökningskontrollen, öppna den nedrullningsbara sökmenyn och filtrera den nedrullningsbara menyn med hjälp av rutnätets kolumnrubrik som visas nedan. En musanvändare (eller pekskärm) kan bara klicka (eller trycka) på någon kolumnrubrik för att komma åt kolumnens filtrerings- och sorteringsalternativ. För en tangentbordsanvändare behöver användaren bara trycka på **Alt**+**Ned** **pil** en gång för att flytta fokus till listrutan då användaren kan använda flikknappen till korrekt kolumn och trycka på **Ctrl**+**G** för att öppna rutnätets nedrullningsbara kolumnrubrikmeny. 

[![gridfilteritemlookup](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png) 

När filtret har använts (se bilden nedan) kan användaren hitta och markera raden som vanligt. 

![filtereditemlookup](./media/filtereditemlookup.png)




