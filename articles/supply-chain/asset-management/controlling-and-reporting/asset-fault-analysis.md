---
title: Felanalys för tillgång
description: I det här avsnittet beskrivs felanalys för tillgång i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectFaultCalculate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e911f7ca3b67acd9d5a1b170d8c99135da730847
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437783"
---
# <a name="asset-fault-analysis"></a>Felanalys för tillgång

[!include [banner](../../includes/banner.md)]

 

I Tillgångshantering kan du analysera tillgångsfelregistrerings för att få en översikt över det totala antalet fel som registrerats under en viss period. Felregistreringar kan analyseras från olika perspektiv, till exempel med fokus på tillgångar, tillgångstyper, funktionsplatser, felsymptom eller feltyper.

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångsfel** > **Felanalys för tillgång**.

2. I dialogrutan **Beräkning av tillgångsfelanalys** kan du använda fältet **Nivå** för att indikera hur detaljerad du vill att tillgångsfelraderna ska vara avseende funktionsplatser. 

    Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla tillgångsfelrader för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå. 
        
    Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla tillgångsfelrader på alla den funktionsplatsnivå som de är relaterade till.

3. Om du vill begränsa sökningen kan du välja specifika tillgångar, feldatum, felorsaker och felåtgärder på snabbfliken **Poster som ska ingå**.

4. Klicka på **OK** för att starta beräkningen.

5. På fliken **Tillgångsfelanalys**, klicka på en eller flera knappar för **Gruppera efter...** för att visa detaljnivån som du vill se. Aktiverade knappar är markerade. Aktivera eller inaktivera knappar genom att klicka på dem.

6. Klicka på **Uppdatera beräkningar** om du vill visa dina val på skärmen. 

>[!NOTE]
>Varje gång du aktiverar eller inaktiverar en knapp för **Gruppera efter**, kom ihåg att klicka på knappen **Uppdatera beräkning**. Detta är nödvändigt eftersom en stor mängd data bearbetas när du räknar om en felsannolikhet.

## <a name="examples"></a>Exempel

Det finns många sätt att analysera felregistreringar. Det här avsnittet har fem exempel på hur olika data ger bättre insikt och detaljrikedom när du analyserar felregistreringar på tillgångar.

### <a name="group-by-symptoms"></a>Gruppera efter symptom

I skärmbilden nedan är bara knappen **Symptom** markerad.

- Felregistreringar har utförts på tre felsymtom: "luftläcka", "utlöst säkring" och "utrustning har fastnat".  
- I kolumnen **Sannolikhet %** blir procentsatserna totalt 100 %. Sannolikheten baseras på alla **symptom** registreringar i den här felanalysen.

![Figur 1](media/06-controlling-and-reporting.png)

### <a name="group-by-symptoms-and-time-period"></a>Gruppera efter symptom och tidsperiod

I bilden nedan läggs **år** och **månad** till för att visa hur du kan visa felregistreringar under en vald period.

- Felsymptomen visas nu som registreringar per år/månad.  
- Om du lägger till alla procentsatser för varje månad i kolumnen **Sannolikhet %** blir procentsatserna totalt 100 %. Sannolikheten baseras på **symptom** registreringarna i den här felanalysen. Om du har ett stort antal rader på en tillgång, men en stor procentsats på en rad, kan det vara en indikation på ett felsymptom som du ska undersöka närmare för att begränsa antalet registreringar för det felsymptomet.

![Figur 2](media/07-controlling-and-reporting.png)

### <a name="group-by-multiple-symptoms-and-assets"></a>Gruppera efter flera symptom och tillgångar

Kombinationen av till gångar och en tillgångstyp används som grund för beräkningarna som visas i på de tre bilderna nedan, vilket ökar detaljnivån.  

I allmänhet innehåller knapparna i åtgärdsfönstergrupperna **Gruppera efter datum**, **Gruppera efter tillgång**, **Gruppera efter funktionsplats** samt knappen **Fel** (Fel-ID) perioder eller tillgångsrelationer. Knapparna **Symptom**, **Område**, **Typ**, **Orsak** och **Åtgärd** är kategoriseringar som används vid felhantering för att analysera registreringar av tillgångsfel och hitta problemområden.  

**Gruppera efter symptom, tillgång och tillgångstyp**

På skärmbilden nedan har **Tillgång** och **Tillgångstyp** lagts till för att ge mer detaljerad information om felregistreringar.

- Felsymptomen delas nu upp i kombinationer av **Tillgång** / **Tillgångstyp** / **Symptom**.  
- I kolumnen **Sannolikhet %**, om du lägger till alla procentandelar för kombinationen av **Tillgång** / **Tillgångstyp** / **Symptom** uppgår var och en till 100 %. Sannolikheten baseras på **symptom** registreringarna i den här felanalysen. Om du har ett stort antal rader på en tillgång, men en stor procentsats på en rad, kan det vara en indikation på ett felsymptom som du ska undersöka närmare för att begränsa antalet registreringar för det felsymptomet.

![Figur 3](media/08-controlling-and-reporting.png)

**Gruppera efter två symptom, tillgång och tillgångstyp**

På skärmbilden nedan har **Område** lagts till i **Symptom**, **Tillgång** och **Tillgångstyp** för att ge fler detaljer om felregistreringar.

- I kolumnen **Sannolikhet %**, om du lägger till alla procentandelar för kombinationen av **Tillgång** / **Tillgångstyp** / **Symptom** på en tillgång uppgår var och en till 100 %. Sannolikheten baseras på kombinationen av **Symptom** och **Område** i den här felanalysen. Om du har ett stort antal rader på en tillgång, men en stor procentsats på en rad, kan det vara en indikation på ett felområde som du ska undersöka närmare för att begränsa antalet registreringar för det felområdet.  

![Figur 4](media/09-controlling-and-reporting.png)

**Gruppera efter tre symptom, tillgång och tillgångstyp**

I skärmbilden nedan läggs **Typ** till, och den mest detaljerade beräkningen i det här exemplet visas.
 
- I kolumnen **Sannolikhet %**, om du lägger till alla procentandelar för kombinationen av **Tillgång** / **Tillgångstyp** / **Symptom** på en tillgång uppgår var och en till 100 %. Sannolikheten baseras på kombinationen av **Symptom**, **Område** och **Typ** i den här felanalysen. Om du har ett stort antal rader på en tillgång, men en stor procentsats på en rad, kan det vara en indikation på en feltyp som du ska undersöka närmare för att begränsa antalet registreringar för den feltypen.

![Figur 5](media/10-controlling-and-reporting.png)


>[!NOTE]
>Om du vill ha en översikt över alla felregistreringar som har skapats på arbetsorder och underhållsbegäranden, klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångsfel** > **Tillgångsfel**. På sidan **Tillgångsfel** väljer du en tillgångsfelregistrering och expanderar fönstret **Relaterad information** för att visa information om den relaterade arbetsordern eller underhållsbegäran.

