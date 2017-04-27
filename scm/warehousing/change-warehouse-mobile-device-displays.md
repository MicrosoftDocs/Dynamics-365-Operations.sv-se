---
title: "Visningsinställningar för mobil lagerställeenhet"
description: "I det här avsnittet beskrivs hur du ställer in utseendet på skärmen på en mobil enhet och hur du mappar kortkommandon till kontroller såsom knappar."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysUserSetup, WHSRFColor, WHSRFColorPicker, WHSWorkUserDisplaySettings
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 29071
ms.assetid: 931a02e8-b561-45e3-9c44-06b875ced1b4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: afa59439e06aad9d669eb352a9837a013f447249
ms.openlocfilehash: 721b293d1f8c76458ca510732f9bb94f003ac6e3
ms.lasthandoff: 03/31/2017


---

# <a name="warehouse-mobile-device-display-settings"></a>Visningsinställningar för mobil lagerställeenhet

[!include[banner](../includes/banner.md)]


I det här avsnittet beskrivs hur du ställer in utseendet på skärmen på en mobil enhet och hur du mappar kortkommandon till kontroller såsom knappar. 

Denna artikel gäller för "avancerad lagerhantering" funktioner i lagerhantering. Mobila enheter kan användas för många av de uppgifter som lagerarbetare.

## <a name="specify-styles-and-map-keyboard-shortcuts"></a>Ange format och mappa kortkommandon
Som en del av den mobila enhetens konfiguration kan du ange olika layouter för mobila enheter. För att göra detta måste du veta namnet på Cascading stillakan (CSS) och Active Server Page utökning (ASPX fil). Standard-filer installeras som en del av lagret mobila enheter Portal installation. Om du inte vet filnamnen, fråga systemadministratören. Du kan definiera en ny stil på den **mobila enhetens skärm inställningar** :

-    I **CSS-filen** , ange namnet på din CSS-filen. Inkludera .css-filtillägg.
-   I den **mobila enheten visa inställningar visa** fältet anger ASPX fil. Inkludera **inte** .aspx filtillägg.

CSS och ASPX filer måste vara placerad i en särskild katalog, så att Internet Information Services (IIS) ansökan kan ladda dem. Det kan vara lämpligt att definiera olika CSS-filer om du använder den mobila enhetens funktionalitet i olika browsers eller på olika typer av hårdvara som kräver olika layout. Enkla inställningar, t.ex. bakgrundsfärg, teckensnitt och teckenstorlek för text, och bredden, och uppförandet av knappar, kan enkelt styras genom användning av CSS-filer. Det ASPX fil används för att visa den mobila anläggningen på server-sidan Asp.net-ansökan. Filen styr hur den övergripande strukturen för HTML är fastställda. Det är en bra idé att anpassa denna funktion endast om du har allvarliga strukturella problem med HTML och JavaScript, och måste ändra koden för din specifika enheter. För att mappa HTML-kontroller på den mobila enheten sidan tangentbordgenvägar, på den **mobila enheten visa inställningssidan** i **kortkommandot** fält, tilldela den numeriska koder för nycklar. Du kan använda **visa koderna för kortkommandon** menyn på den mobila enheten att hitta numeriska teckenkoder. Observera att kartläggningar kan variera beroende på maskinvara som används. Du måste använda följande syntax för att skapa mappningen:

&lt;kontrollnamn&gt;(&lt;tangentnamn&gt;)=&lt;tangentkodkod&gt;;

Här följer en förklaring av de delar av syntaxen:

-   **&lt;kontrollnamn&gt;** – Namnet på kontrollen, till exempel en knapp, som renderas i HTML-format.
-   **(&lt;tangentnamn&gt;)** – Namnet på den tangent på tangentbordet som du skapar en genväg för.
-   **&lt;Tangentkod&gt;** – Den numeriska teckenkoden för den tangent som ska användas som genväg.

Här är ett exempel:

Cancel(Esc)=27; Full(F2)=113

På alla sidor som innehåller en **Avbryt-** knapp kommer denna text:

**(ESC) Avbryt**

Tryck på Esc-tangenten på tangentbordet för att aktivera **knappen Avbryt** . Att tillämpa stil och kortkommandon inställningar till en specifik enhet, måste du skapa en mappning i **kriterierna** . Du måste använda en .NET regelbundet uttryck för att skapa kartor och uttrycket skall bestå av tre delar som åtskiljs av ett vertikalt streck (|), så här:

Request.UserHostAddress=&lt;användarens värdadress&gt;|HostName=&lt;användarens värdnamn&gt;|Request.UserAgent=&lt;användarens agent&gt;

Här följer en förklaring av de olika delarna i uttryck:

-   **&lt;användarens värdadress&gt;** – Ett .NET-uttryck av standardtyp som matchar den begärandes IP-adress.
-   **&lt;användarens värdnamn&gt;** – Ett .NET-uttryck av standardtyp som matchar den begärandes nätverksnamn.
-   **&lt;användaragent&gt;** – Ett .NET-uttryck av standardtyp som matchar identifieraren för den begärandes webbläsare.

Följande exempel gör Internet Explorer 8 att användas:

Request.UserHostAddress=.\*|HostName=.\*|Request.UserAgent=MSIE\\s8\\.0

Du kan använda **Visa serverkonfiguration för visningsinställningar** menyn på mobila enheten för att hitta information om installationen.

## <a name="define-text-colors-for-messages"></a>Definiera text färger för meddelanden
Du kan använda **mobila enheten textfärger** sida att styra olika färger som används i system-meddelanden, t.ex. felmeddelanden. Exempelvis textfärg kan ange ändamålet eller allvarlighetsgrad. Följande typer av meddelanden visas.

| Meddelandetyp | Beskrivning                                                                                                                                                                            |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Standard      | Standardmeddelanden använda standardinställningarna för färg alla meddelanden, såsom de definieras i CSS-filen för Warehouse Mobile Device Portal.                                                   |
| Fel        | Felmeddelanden anger ett problem som användaren måste lösa innan han eller hon kan fortsätta.                                                                                             |
| Lyckades      | Framgång meddelanden bekräfta att en åtgärd har lyckats.                                                                                                                                |
| Varning      | Varningsmeddelanden informerar de arbetstagare som det är en fråga, eller att det kan vara en fråga om arbetstagaren fortsätter. Men arbetstagaren inte har att lösa problemet att fortsätta. |

För att välja färg, **välj färg** , klicka i paletten eller typ en hexadecimal färgkod.

## <a name="define-the-date-format-to-use-on-mobile-devices"></a>Definiera det datumformat som ska användas i mobila enheter
Du kan även utöka listan över godkända datumformat för varje installationen. Denna funktion kan vara användbar om du t.ex. vill ge ett format som gör det lättare för en arbetstagare att ange datum på en mobil enhet. Standardformat bestäms av användarens språk, som anges i fältet **språk** på sidan **Användaralternativ**. (Samma sida används också för att koppla en medarbetare till en specifik lagerarbetare.) **Obs!** Lagerställets portal för mobila enheter använder inte inställningen för fältet **Format för datum/tid och nummer** på sidan **Inställningar för språk och region**. Om du vill ändra datumformat, du måste vara bekant med regelbundna uttryck i den Microsoft .NET ramen. För mer information, se [.NET Framework regelbundna uttryck](http://go.microsoft.com/fwlink/?LinkId=391260). För att definiera datumformat, redigera filen datum.ini som finns på Innehåll\\Inställningar\\Dates.ini på portalservern för lagerställets mobila enheter. Denna fil använder .NET reguljära uttryck för att ange datumformat. Den regelbundna uttryck måste innehålla deluttryck att skapa namngivna grupper för dag, månad och år (ddmmåå), vilket visas i följande exempel:

^(?&lt;dag&gt;\\d{2})(?&lt;månad&gt;\\d{2})(?&lt;år&gt;\\d{2})$

Varje deluttrycket kräver en till två siffror för månad och dag, och en till fyra siffror för året. I följande exempel deluttrycket definierar en namngiven grupp under ett år, och kräver ett minimum av två siffror eller högst fyra siffror:

(?&lt;år&gt;\\d{2,4})

Du kan ange mer än ett uttryck i samma fil. Varje uttryck måste vara på en separat rad. Det första uttrycket som matchas används för att parsa datum.

<a name="see-also"></a>Se även
--------

[Konfiguration av mobila enheter för lagerarbete](configure-mobile-devices-warehouse.md)




