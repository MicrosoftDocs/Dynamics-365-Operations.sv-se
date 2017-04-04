---
title: "Använda sökningar för att söka efter information"
description: "I Microsoft Dynamics 365 för operationer har många fält sökningar som hjälper dig att enkelt hitta rätt eller önskat värde. Flera förbättringar har lagts till sökningar kontrollerna mer användbara och gör användarna mer produktiva. I det här avsnittet lär dig om funktionerna uppslag och får några användbara tips för att få optimal användning av sökningar i systemet."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 6a25593632575dcd71fa4a3c9cf5b83c9f8ecd39
ms.lasthandoff: 03/31/2017


---

# <a name="use-lookups-to-find-information"></a>Använda sökningar för att söka efter information

I Microsoft Dynamics 365 för operationer har många fält sökningar som hjälper dig att enkelt hitta rätt eller önskat värde. Flera förbättringar har lagts till sökningar kontrollerna mer användbara och gör användarna mer produktiva. I det här avsnittet lär dig om funktionerna uppslag och får några användbara tips för att få optimal användning av sökningar i systemet.  

<a name="responsive-lookups"></a>Effektiv sökning
------------------

I tidigare versioner av Dynamics 365 för operationer när du kommunicerar med en sökkontroll skulle användarna behöver göra något explicit för att öppna den nedrullningsbara menyn. Kan ha uppstått genom att skriva en asterisk (\*) att klicka på listrutan i kontrollen att filtrera sökningen baseras på det aktuella värdet för kontrollen eller genom att den **Alt**+**NEDPIL** kortkommando. Sökning efter kontroller har ändrats så att bättre överensstämma med gällande praxis för webbplatsen:

-   Sökning efter menyerna ska nu öppnas automatiskt efter en liten paus i att skriva med nedrullningsbara menyinnehåll filtrerad efter sökning kontrollens värde.
    -   Observera att den gamla funktionen hos den nedrullningsbara listan automatiskt öppnas när du har skrivit en asterisk (\*) har ersatts.
-   När listrutan sökning har öppnat sker följande:
    -   Markören kvar i sökkontroll (i stället för att fokus flyttas till den nedrullningsbara menyn) så att du kan fortsätta att göra ändringar i kontrollens värde. Användaren kan dock fortfarande använda den **UPPIL** och **NEDPIL** ändra raderna i den nedrullningsbara menyn och ange om du vill markera hela raden på menyn.
    -   När ändringar görs i sökfältet kontrollvärde justeras innehållet i den nedrullningsbara menyn.

Tänk dig ett uppslagsfält som kallas **ort**. 

Om fokus är i den **ort** fält du kan börja leta efter orten genom att skriva ett par bokstäver som "kolumn".  Efter du slutat skriva öppnas sökningen automatiskt, filtrerat så att de orter som börjar med "kolumn". 

[![typeaheadLookupExample](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png) 

Nu är markören kvar i sökfältet. Om du fortsätter att skriva värdet är "kolumner" justeras sökning efter innehållet automatiskt så att den avspeglar det senaste värdet i kontrollen. 

![updateFilterLookupExample](./media/updatefilterlookupexample.png) 

Även om fokus i sökfältet kontrollen, kan du också använda de **UPPIL** eller **NEDPIL** för att markera den rad som du vill markera. Om du trycker på **ange** väljs den markerade raden från sökningen och kontrollens värde uppdateras. 

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>Skriva i mer än ett ID-nummer
När du anger data är naturligt för en användare försöker identifiera en enhet, till exempel en kund eller leverantör med avseende på namnet i stället för en identifierare som representerar enheten. I den aktuella versionen av Dynamics 365 för inmatning många (men inte alla) sökningarna nu sammanhangsberoende. Kraftfulla funktionen kan användaren ange ID: T eller motsvarande namn i sökfältet kontrollen. 

Anta de **kundkonto** när du skapar en försäljningsorder. Det här fältet visas den **konto-ID** för kunden, men en användare normalt skulle föredra att träda in en **kontonamnet** i stället för en **konto-ID** för det här fältet när du skapar en försäljningsorder, till exempel "Skogen Wholesales" istället för "US-003".

Om användaren har börjat att ange en **konto-ID** i kontrollen sökning på undermenyn är automatiskt enligt beskrivningen i föregående avsnitt så att användaren ser sökningen enligt nedan.

[![Sammanhangsbaserad sökning när ett kundkonto-ID har angetts](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)

Användaren kan emellertid också ange början på en **kontonamnet** också. Om detta inträffar visas följande sökfunktionen användaren. Meddelande hur **namn** kolumnen flyttas till den första kolumnen i sökningen och hur sökningen sorteras och filtreras utifrån de **namn** kolumn.

[![Sammanhangsberoende sökning när en kunds namn anges.](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>Med hjälp av rutnätet kolumnrubriker för mer avancerad filtrering och sortering
Sökning efter förbättringarna beskrivs i de föregående punkterna avsevärt förbättra användarnas möjlighet att navigera raderna i en sökning baserat på en "börjar med" sökning i den **ID** eller **namn** i sökningen. Det finns dock situationer då mer avancerad filtrering (eller sortering) behövs för att hitta rätt rad. I sådana fall måste måste användaren du använder alternativen för filtrering och sortering i rutnätet kolumnrubriker i sökningen. Anta exempelvis att en medarbetare registrerar en försäljningsorderrad som behöver hitta rätt "kabel" som produkten. Skriv "kabel" i den **artikelnummer** kontroll inte är användbart eftersom det inte finns några produktnamn som börjar med "kabel." 

![emptyitemlookup](./media/emptyitemlookup.png) 

Användaren måste istället Radera värdet i kontrollen sökning, öppna listrutan Sök och filtrera på undermenyn med hjälp av kolumnrubriken rutnät som visas nedan. En mus (eller pekskärm) användare kan bara klicka (eller tryck) alla kolumnrubriker för att komma åt de filtrerings- och sorteringsalternativ för kolumnen. För en grupp användare användaren behöver bara trycka på **Alt**+**ned****pil** en gång för att flytta fokus till listrutan då användaren kan Tabba till kolumnen korrekt och tryck **Ctrl**+**G** att öppna rutnätet nedrullningsbara kolumnrubrikmenyn. 

[![gridfilteritemlookup](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png) 

När filtret har använts (se bilden nedan) är användaren hitta och markera raden som vanligt. 

![filtereditemlookup](./media/filtereditemlookup.png)


