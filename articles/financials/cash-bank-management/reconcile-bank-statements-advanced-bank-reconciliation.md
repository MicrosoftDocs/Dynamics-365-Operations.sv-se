---
title: Stämma av bankutdrag med hjälp av avancerad bankavstämning
description: Funktionen Avancerad bankavstämning låter dig importera elektroniska bankutdrag och utföra en automatiskt avstämning mot banktransaktioner i Microsoft Dynamics 365 for Finance and Operations. Det här ämnet innehåller en beskrivning av avstämningsprocessen.
author: saraschi2
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationWorksheet
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 98243
ms.assetid: 9df13adf-aa9d-4f6b-bde6-25a214611692
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6fc63edd47b6067b4dc0152c62e0cd6e77acaad
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842291"
---
# <a name="reconcile-bank-statements-by-using-advanced-bank-reconciliation"></a>Stäm av bankutdrag med hjälp av avancerad bankavstämning

[!include [banner](../includes/banner.md)]

Funktionen Avancerad bankavstämning låter dig importera elektroniska bankutdrag och utföra en automatiskt avstämning mot banktransaktioner i Microsoft Dynamics 365 for Finance and Operations. Det här ämnet innehåller en beskrivning av avstämningsprocessen.  

<a name="import-an-electronic-bank-statement"></a>Importera ett elektronisk bankutdrag
-----------------------------------

Du kan importera dina bankutdrag med hjälp av åtgärden **Importera utdrag** på sidan **Bankutdrag**. På bankutdraget identifieras bankkontot genom en kombination av värden som anges i informationen om bankkontot. Dessa värden är bankens namn, bankkontonummer, organisationsnummer, SWIFT-kod och IBAN-nummer. 

Du kan överföra ett bankutdrag som innehåller information om antingen ett enskilt konto eller flera konton. Om det finns flera konton kan kontona vara olika juridiska personer.

-   Om du vill importera en enskild bankutdragsfil för ett enskilt konto, ställ in alternativet **Importera utdrag för flera bankkonton i alla juridiska personer** på **Nej** och välj det bankkonto som är associerat med utdraget. Klicka på **Bläddra** för att välja den associerade bankutdragsfilen och klicka sedan på **Överför**.
-   Om du vill importera en enstaka bankutdragsfil för flera konton, ställ in alternativet **Importera utdrag för flera bankkonton i alla juridiska personer** på **Ja**. Klicka på **Bläddra** för att välja den associerade bankutdragsfilen och klicka sedan på **Överför**.

Om några utdrag i en elektronisk fil inte kan kopplas till ett bankkonto med hjälp av identifieringsfälten ska de inte importeras. Du kan dock fortfarande importera andra utdrag i filen. Användaren får sedan ett meddelande med information om att importen av bankutdraget misslyckades för specifika bankkonton. Observera att användaren som importerar bankutdraget måste ha åtkomst till en juridisk person för att importera utdrag för den juridiska personens bankkonton. 

Du kan använda en zip-fil för att överföra flera utdragsfiler till Finance and Operations i en enda process. Om du vill importera flera bankutdragsfiler för flera konton kan du slå samla alla bankutdragsfiler i en zip-fil. I dialogrutan **Importera bankutdrag**, ställ in alternativet **Importera utdrag för flera bankkonton i alla juridiska personer** på **Ja**. Klicka på **Bläddra** för att välja zip-filen som innehåller bankutdragsfilerna och klicka sedan på **Överför**. Importeringsprocessen kommer att känna igen zip-filen och överföra varje utdrag som är inkluderade i den, oavsett bankkontots juridiska person. 

Alternativet **Stäm av efter import** är tillgängligt. När det här alternativet är inställt på **Ja** validerar systemet kontoutdraget, skapar en ny bankkontoavstämning och ett nytt kalkylblad och kör standarduppsättningen för matchningsregler när bankutdraget överförs. Den här funktionen automatiserar processen fram till den punkt där transaktionen måste stämmas av manuellt.

## <a name="validate-the-bank-statement"></a>Validera bankutdraget
Klicka på **Validera** på sidan **Bankutdrag** om du vill validera ett utdrag. Bankutdrag måste valideras innan de kan stämmas av. Det här steget slutförs automatiskt om alternativet **Stäm av efter import** är inställt på **Ja** vid tidpunkten för importen. 

Vid bankutdragsvalideringen verifieras att:

-   bankutdraget matchar det valda bankkontot
-   valutan på bankutdraget matchar valutan för det valda bankkontot
-   den ingående balansen på utdraget är lika med den utgående balansen på föregående utdrag för bankkontot
-   datumet inte överlappar datumet för olika bankutdrag för samma bankkonto
-   det inte finns några luckor i datumen på bankutdraget
-   datumen på utdragets rader är mellan från-datumet och till-datumet på bankutdraget
-   den ingående balansen och beloppet på summaraden är lika med den utgående balansen.

När valideringen är slutförd uppdateras statusen på bankutdraget till **Validerat**. Ett bankutdrag måste valideras innan det kan stämmas av.

## <a name="reconcile-the-bank-statement"></a>Stämma av bankutdraget
När du har importerat ett elektroniskt bankutdrag och validerat det på sidan **Bankutdrag** kan du stämma av det med hjälp av sidorna **Bankavstämning** och **Kalkylblad för bankavstämning**. 

På sidan **Bankavstämning**, klicka på **Ny** för att skapa en ny avstämning och välj sedan bankkonto för utdraget som importerades. Ett bankkonto kan endast ha en öppen bankavstämning. Slutdatumet fastställer vilka bankutdragstransaktioner och Dynamics Operations-banktransaktioner som är inkluderade i avstämningskalkylbladet. Som standard används det aktuella systemdatumet som slutdatum, men du kan ändra datum för avstämningen. Den återstående huvudinformationen hämtas automatiskt från utdraget. Det här steget slutförs automatiskt om alternativet **Stäm av efter import** är inställt på **Ja** vid tidpunkten för importen. 

På sidan **Bankavstämning**, klicka på **Kalkylblad** för att öppna sidan **Kalkylblad för bankavstämning**. Om alternativet **Stäm av efter import** är inställt på **Ja** kommer standarduppsättningen för matchningsregeln att köras automatiskt för avstämningen. Om du vill köra matchningsregler manuellt klickar du på **Kör matchningsregler** för att välja vilka matchande regeluppsättningar eller matchningsregler som ska köras mot banktransaktionerna. Om du har många transaktioner att bearbeta kan du slutföra det här steget som en batchprocess. 

Sidan **Kalkylblad för bankavstämning** har fyra rutnät som innehåller transaktioner. De två övre rutnäten visar transaktioner från bankutdraget och Dynamics Operations som ännu inte har stämts av. De två nere rutnäten visar avstämda transaktioner. Fliken **Transaktionsdetaljer för bankutdrag** visar information om den bankkontoutdragstransaktion som inte är avstämd och som är markerad i det övre rutnätet. 

Det finns tre metoder för att matcha eller stämma av bankutdragstransaktioner:

-   Matcha transaktioner med Dynamics Operations-banktransaktioner.
-   Matcha transaktioner med en bankutdragstransaktion för återföring.
-   Markera transaktionen som **Ny**, så att den kan bokföras senare som en banktransaktion i Finance and Operations.

Om du vill matcha transaktioner manuellt, väljer du transaktionerna i rutnätet **Bankutdragstransaktioner**, markerar motsvarande transaktioner i rutnätet **Operations-banktransaktioner** och klickar sedan på **Matcha**. De valda transaktionerna flyttas från det övre rutnäten för omatchade transaktioner till de nedre rutnäten för matchade transaktioner. Dessutom uppdateras de matchade och omatchade totalbeloppen. Du kan ha ett-till-ett-, många-till-en- och många-till-många-transaktionsmatchningar. Matchningar måste följa reglerna för tillåtna datumskillnader och transaktionstypsmappning. Dessa regler ställs in på sidan **Parametrar för kassa- och bankhantering**.

Öresdifferenser kan uppstå i din avstämning. Du kan matcha en enskild bankutdragstransaktion och en enstaka Dynamics Operations-banktransaktion som har öresdifferenser om öresdifferenserna ligger inom det toleransbelopp som definieras på sidan **Tillåten öresdifferens** på bankkontot. Beloppet visas i fältet **Korrigeringsbelopp** på den matchande Operations-banktransaktionen. När bankavstämningen markeras som avstämt, bokförs korrigeringar automatiskt genom att använda huvudkontot som definieras på den associerade banktransaktionstypen. Korrigeringar stöds inte för dokumenttyperna **Check** och **Insättning**. 

Återföringar av bankutdragstransaktioner matchas med hjälp av kalkylblad för avstämning. Två utdragsrader kan matchas om beloppen är motsatta och om någon av transaktionerna har markerats som en återföring. Du kan också ställa in en matchningsregel för åtgärden **Rensa alla återföringsutdragsrader**.

Återförda Dynamics Operations-banktransaktioner måste stämmas av med hjälp av sidan **Dynamics Operations-banktransaktioner**. Du kan stämma av två Dynamics Operations-banktransaktioner tillsammans om dokumenten har samma bankkonto, dokumenttyp och betalningsreferens och om de har motsatta belopp. Du kan även stämma av en enstaka avbruten kontroll för att förhindra att de transaktionerna visas i kalkylbladet för avstämning. 

Om det finns nya bankinitierade transaktioner såsom räntor, avgifter och skatter som ännu inte är införda i Finance and Operations kan du lägga till dem i en journal som är associerad med den valda bankutdragsavstämningen. Välj en bankutdragstransaktion i rutnätet **Bankutdragstransaktioner** för ej matchade transaktioner och klicka sedan på **Markera som ny**. Statusen för transaktionen markeras som **Ny** och transaktionen flyttas till rutnätet **Bankutdragstransaktioner** för matchade transaktioner. Du ska bokföra en transaktion som är markerad som **Ny** senare, från sidan **Bankutdrag**. 

Du kan ta bort matchning för transaktioner som matchades felaktigt. Markera den matchade bankutdragstransaktionen och klicka sedan på **Omatchad**. Alla kopplade transaktioner flyttas tillbaka till det övre rutnätet för ej matchade transaktioner och de matchade och omatchade totalbeloppen uppdateras. 

När du väl har slutfört din avstämningsprocess bör du märka kalkylbladet för bankavstämning som "avstämt".  Denna process kommer använda de konton som angetts på sidan **Banköverföringstyp** för att bokföra korrigeringsbelopp automatiskt.  Bankavstämningen för ett utdrag kan när som helst markeras som "avstämt", även om det finns bankutdragsrader som ännu inte har matchats.  Icke-matchade transaktioner kommer automatiskt att flyttas till nästa avstämnings-kalkylark i form av icke-matchade utdragstransaktioner som ska stämmas av.  Notera att en bankutdragsavstämning som har markerats som "avstämt" inte kan ändras.  Avstämningen kommer inte längre att kunna ändras, och du förlorar därför möjligheten att uppdatera avstämningen.

## <a name="post-new-transactions-that-are-associated-with-the-reconciliation"></a>Bokföra nya transaktioner som är kopplade till avstämningen
En bankutdragstransaktion som har markerats som **Ny** på kalkylbladet för avstämning bokförs på sidan **Bankutdrag**. På sidan **Bankutdrag**, markera utdrags-ID för att visa detaljer om utdraget. I menyn **Redovisning** kan du använda alternativen **Visa fördelningar** och **Visa redovisning** för att visa detaljerna för de nya transaktionerna och tillhörande redovisningsposter. Välj alternativet **Bokför** för att bokföra en bankutdragsrad som är markerad som **Ny** i redovisningen. Observera att bokföringen enbart kan slutföras en gång per bankutdrag.



