---
title: Konfigurera och arbeta med orderspärrar för kundtjänst
description: Denna artikel beskriver hur du arbetar med undantag för order med Dynamics 365 Commerce.
author: josaw1
ms.date: 05/14/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans, MCROrderEventSetup, MCROrderEventTable
audience: Application User
ms.reviewer: josaw
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 1f8c5daecc6aa05cc6a0f5dc4a2bc44a0fbba07d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860147"
---
# <a name="configure-and-work-with-call-center-order-holds"></a>Konfigurera och arbeta med orderspärrar för kundtjänst

[!include [banner](includes/banner.md)]

Denna artikel beskriver de funktioner för spärrad order som Dynamics 365 Commerce har för kundtjänstorder.

## <a name="configuring-call-center-order-holds"></a>Konfigurera orderspärrar för kundtjänst

Om du vill använda funktioner för kundtjänstorder måste du först definiera undantagskoder Om du vill skapa en uppsättning användardefinierade koder baserade på dina affärskrav, gå till **försäljning och marknadsföring**\>**inställningar**\>**försäljningsorder**\>**koder för spärrad order**. Du kan även flagga en av spärrningskoderna som håller standardkoden genom att ange alternativet **standard för försäljningsorder** till **Ja** för den. Denna spärrkod kommer att användas varje gång en försäljningsorder har spärrats. Om en försäljningsorder har reserverat lager och reservationer måste tas automatiskt bort om ordern placeras på grund av en viss orsak, ange alternativet **ta bort lagerreservationer** till **Ja** för orsakskoderna.

Om du vill ange vilken typ av notering som kommer skapas när användare spärrar en försäljningsorder med valfria noteringar, gå till **kundreskontra**\>**inställningar**\>**parametrar för kundreskontra**, och klicka sedan på snabbfliken **försäljningsinställningar** på fliken **allmänna** och ställ in fältet **noteringstyp**. Använd fältet **Spärrad försäljningsorderstatus** för att definiera den färg som kommer att användas för att markera försäljningsorder till spärrad när de visas på sidan **kundtjänst**.

Skapa orsakskoder för ett valfritt antal undantag genom att gå till **Butik och handel** \> **kanalinställningar** \> **Infokoder**. Dessa infokoder kan användas som en sekundär orsakskod för att definiera ytterligare huvudsakliga spärrkoden. Välj **Ny** för att skapa en orsakskoduppsättning och därefter **delkoder** för att definiera listan med ytterligare orsaker. Om du vill länka alla infokoder som du definierar för kundtjänstkanal gå till **Butik och handel** \> **kanaler** \> **kundtjänst** \> **alla kundtjänster**. På snabbfliken **allmänna** ställ in fältet **Spärrkod**.

## <a name="putting-orders-on-hold"></a>Spärrade order

Order som kundtjänst skapar i back officnäthandelsprogrammet kan spärras manuellt eller automatiskt i specifika situationer.

Under orderregistreringen och innan beställningen gjordes och bekräftades ska användare kunna lägga order manuellt eller spärra för att förhindra att de övergår till distributionslagret för vidare bearbetning. Till exempel om kunden som gör beställningen inte är redo eller viktiga data som krävs för att bearbeta ordern kanske saknas.

På orderns startsida kan användaren av kundtjänst spärra en order med hjälp av alternativet **Orderspärrar** på fliken **försäljningsorder** på orderregistreringsmenyn. Alternativt kan användaren välja menyobjektet **Spärra** på sidan **Sammanfattning av försäljningsorder** som visas när användaren väljer **Slutförd** på en kundtjänsts försäljningsorder.

I båda fallen visas sidan **Orderspärrar**. Användaren kan sedan välja **Ny** för att skapa ett undantag för ordern. I fältet **spärrkod** ska användaren välja den kod som bäst beskriver orsaken till spärrningen. I fältet **orsakskod** kan användaren också välja en ytterligare kod för att skapa en andra beskrivning av spärrningen.

På snabbfliken **anteckningar** i fältet **spärranteckningar** kan användaren ange ytterligare friformsanteckningar för att ange ytterligare sammanhang eller information om spärrningen. Dessa anteckningarna kan hjälpa andra användare att granska och arbeta med spärrordern senare.

När spärrningsinformation registrerats och sparats, kan användaren stänga sidan **Orderspärrar**. Användaren går sedan tillbaka till startsidan för försäljningsordern. Om inga ytterligare åtgärder krävs på försäljningsordern, stänger användaren startsidan för försäljningsorder.

Om flaggan **aktiverar slutförande av order** är aktiverad i kundtjänstkanalen behöver betalningen inte gälla för en order som har spärrats. Däremot för en försäljningsorder som inte är spärrad kan användarna inte lämna startsidan för försäljningsorder förrän betalningen görs. Betalning kommer förstås att krävas innan orderspärren frisläpps.

Kundtjänst kan dessutom lägga en manuell bedrägerispärr för order som av någon anledning är osäkra. Order kan också spärras automatiskt när de matchar aktiva bedrägerikriterier och regler. Mer information om den här typen av orderspärr, se [konfigurera bedrägerivarningar](/dynamics365/unified-operations/retail/set-up-fraud-alerts).

## <a name="viewing-and-managing-orders-that-are-on-hold"></a>Visa och hantera de order som har spärrats

### <a name="viewing-hold-information-for-a-single-sales-order"></a>Visa spärrinformation om en enskild försäljningsorder

På sidan **kundtjänst** kan användare visuellt identifiera order som är spärrade eftersom orderraderna markeras med en viss färg. Färgen som definieras av fältet **Spärrad försäljningsorderstatu** på sidan **parametrar för kundreskontra**.

> [!NOTE]
> Om raden väljs på sidan visas inte markeringsfärgen.

Användare kan också visa detaljerad statusinformation för en försäljningsorder för att lära dig mer om ordern är spärrad. Detaljerad statusinformation är tillgänglig från sidan **alla försäljningsorder** eller **kundtjänst**. Om en order har spärrats, anges flaggan **Bearbeta inte** och fältet **Detaljerad status** visar status av antingen **spärrad** eller **bedrägerispärr** beroende på scenariot.

Om du vill visa information om en enskild orderspärr kan användare öppna en detaljerad vy över sidan **orderspärr** från sidan den **kundtjänst** genom att välja menyn **alternativ** för den valda försäljningsordern. Användare kan också komma åt den här vyn från sidan **alla försäljningsorder** genom att välja menyobjektet **Orderspärrar** på fliken **försäljningsorder**.

### <a name="viewing-all-orders-that-are-on-hold"></a>Visa alla order som har spärrats

För att visa alla order som har spärrats manuell eller automatisk, gå till **Butik och handel** \> **kunder** \> **orderspärrar**.

Workbench **Orderspärrar** visar lista över alla order som har spärrats på grund av manuella eller bedrägerirelaterade spärråtgärder. Genom att utnyttja standardfiltrerings- och sorteringsalternativen på sidan kan användarna skapa vyer som låter dem arbeta med eller hantera specifika spärrkoder som de ansvarar för att granska. Workbench **Orderspärrar** anger även antalet dagar som en order har spärrats. Den här informationen hjälper användarna att prioritera kön.

För att få en mer detaljerad vy över de order som har spärrats kan användare välja alternativet **Orderspärr** på menyn. Den här vyn ger information om kunden, noteringar som har kopplats till ordern, kund eller spärråtgärd. Vyn innehåller även information om orsaken till att automatisk spärr visas om ordern spärrades eftersom den matchar en bedrägeriregel.

Både från listvyn och detaljerad vy över sidan **Orderspärrar** kan användare visa eller redigera ytterligare orderrelaterad information, såsom betalningar, summor och anteckningar.

Alternativen på fliken **Spärra betalning** är praktiskt om flera användare arbetar med spärrkön samtidigt. Genom att välja alternativet **kassa** kan användarna ange att de arbetar för att granska och undersöka orderspärren. På så sätt behöver andra användare inte slösa tid med att försöka utföra samma arbete. Från en detaljerad vy över sidan **Orderspärrar** kan användare visa information om kassadatum och tid och användaren som har checkat ut spärrposten.

När en spärrpost är utcheckat kan bara användaren som har checkat ut radera kassa. Denna begränsning är avsedd för att förhindra att användare tar poster som andra användare redan arbetar med. För att släppa en order tillbaka till kön så att andra användare kan arbeta med den väljer den användare som checkade ut posten alternativ **Rensa kassa**.

> [!NOTE]
> Spärren frisläpps inte när kassa är rensad.

I vissa situationer, t.ex. när en användare är sjuk eller har lämnat företaget, kanske poster som är utcheckade till användaren tilldelas en annan användare. En chef kan tilldela om poster med hjälp av alternativet **Åsidosätt kassa**.

## <a name="releasing-orders-that-are-on-hold"></a>Frisläppa order som har spärrats

I både listvyn och detaljerad vy över sidan **Orderspärrar**, innehåller fliken **rensa spärr** de alternativ som används för att frisläppa en orderspärr. Använd alternativet **rensa spärrar** för att frisläppa en order från den valda spärrkoden.

Kundtjänstorder kräver betalning. Därför kan en spärr inte rensas helt om inte betalning har tillämpats på ordern. På sidan **kundtjänstparametrar** på fliken **spärrar** kontrollerar du att parametern **Skicka efter rensning** är aktiverad. Den här inställningen kan garantera att en rensad spärrorder genomgår korrekt ordningsföljd för sändningslogik för verifiering och auktorisering av betalningar. Om betalningar saknas får användaren ett felmeddelande och spärrkoden avmarkeras inte.

Om parametern **Skicka efter rensning** inte har angetts bör användaren använda alternativet **rensa och skicka** på menyn **rensa spärr** för att säkerställa att ordern går igenom alla nödvändiga betalningsvalideringar. Om orderöverföringen misslyckas när flaggan **Aktivera slutförande av order** är aktiverad i kundtjänstkanal kommer ordern har frisläppts från dess spärrstatus men flaggan **Bearbeta inte** förblir inställd. Därför släpps inte ordern till lagret förrän rätt betalningar har tillämpat och valideras.

Om användaren vill ta bort ett undantag, men gör ytterligare ändringar i ordern innan den frisläpps för vidare bearbetning, kan de välja alternativet **rensa och ändra**. Det här alternativet tar bort spärrkoden och öppnar försäljningsorderinformation så att användare kan göra ytterligare ändringar i ordern. Användare kan också koppla betalningen och skicka försäljningsordern genom betalningsvalideringslogik när flaggan **aktiverar slutförande av order** är aktiverad i kundtjänstkanalen.

## <a name="reporting-options"></a>Rapporteringsalternativ

Gå till **Butik och handel** \> **förfrågningar och rapporter** \> **kundtjänstrapporter** \> **Orderspärrrapport** om du vill köra en rapport om orderspärrar efter datumintervall, spärrkod eller andra relaterade kriterier.


[!INCLUDE[footer-include](../includes/footer-banner.md)]