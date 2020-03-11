---
title: Rutnätsmöjligheter
description: I det här avsnittet beskrivs flera kraftfulla funktioner i rutnätskontrollen. Den nya rutnätsfunktionen måste aktiveras för att du ska kunna använda dessa funktioner.
author: jasongre
manager: AnnBe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7136edba828bf97b6e0c8d2a698b884640d680e5
ms.sourcegitcommit: 880f617d1d6e95eccbed762c7ea04398553c2ec0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036275"
---
# <a name="grid-capabilities"></a>Rutnätsmöjligheter

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Den nya rutnätskontrollen innehåller flera användbara och kraftfulla funktioner som kan användas för att förbättra användarproduktiviteten, skapa mer intressanta vyer av dina data och få meningsfulla insikter om dina data. Den här artikeln kommer att omfatta följande funktioner: 

-  Beräknar summor
-  Gruppera data
-  Skriva före systemet
-  Utvärdera matematikuttryck 

## <a name="calculating-totals"></a>Beräknar summor
I Finance and Operations-appar har användare möjlighet att visa summor längst ned på numeriska kolumner i rutnät. Dessa summor visas i ett sidfotsavsnitt längst ned i rutnätet. 

### <a name="showing-the-grid-footer"></a>Visa rutnätets sidfot
Det finns ett sidfotsområde längst ned i alla tabell rutnät i Finance and Operations-program. Sidfoten kan visa värdefull information som är relaterad till de data som visas i rutnätet. Här följer några exempel på denna information:

- Antalet markerade rader i tabellen (om fler än en post har valts)
- Total summor längst ned i konfigurerade numeriska kolumner
- Antalet rader i datauppsättning 

Den här sidfoten är som standard dold, men den är lätt att aktivera. Om du vill visa sidfoten för ett rutnät högerklickar du på en kolumn rubrik i rutnätet och väljer alternativet **Visa sidfot**. När sidfoten har aktiverats för ett visst rutnät kommer denna inställning att kommas ihåg tills användaren väljer att dölja sidfoten, som du kan göra genom att högerklicka på en kolumnrubrik och välja **Dölj sidfot**.  Observera placeringen av åtgärden **Visa sidfot/Dölja sidfot** förväntas ligga i en senare uppdatering. 

### <a name="specifying-columns-with-totals"></a>Ange kolumner med summor
För närvarande kommer inga kolumner att konfigureras för att visa summor som standard. I stället betraktas detta som en enstaka inställningsaktivitet, på samma sätt som du justerar bredden på kolumner i rutnät. När du har angett att du vill visa summorna för en kolumn kommer den inställningen att komma ihåg nästa gång du besöker sidan.  

Du kan konfigurera en kolumn på två sätt för att visa en summa: 

- Högerklicka i kolumnen som du vill se summa för och välj sedan **Summa den här kolumnen**. Den här åtgärden medför att tre händelser inträffar:

    1. Sidfoten blir synlig. 
    2. Din preferens för att se summan för den här kolumnen sparas. 
    3. En beräkning av summor initieras för den här kolumnen och alla andra kolumner som du tidigare har konfigurerat för att se summor för. Den tid som krävs för att visa en summa beror på storleken på den datauppsättning som du summerar.

- När sidfoten är synlig väljer du **Visa summa** i sidfotsområdet längst ned i kolumnen som du vill se en total summa för. Om det inte finns några konfigurerade kolumner visas knappen **Visa summa** för alla numeriska kolumner. 

    När minst en kolumn har konfigurerats för summor, kommer knapparna **Visa summa** endast att vara tillgängliga vid hovring eller fokus. Om du väljer **Visa total** sparar du bara din inställning för att se en summa i den här kolumnen, så att inställningen tillämpas vid framtida besök på sidan. I sidfoten markeras det här läget med ett streck som visas i kolumnen. (Alternativt, om datauppsättning är tillräckligt litet visas en summa omedelbart.)

Om du gör ett misstag och inte längre vill se en summa i en viss kolumn högerklickar du på kolumnen och väljer **Dölj summa** eller väljer knappen **Dölj summa** i sidfoten i den kolumnen. Den här inställningen kommer också att sparas för framtida besök på sidan. 

### <a name="calculating-totals"></a>Beräknar summor
När du kommer till en sida med sidfoten synlig och kolumner som redan konfigurerats för summor kan det hända att summorna inte visas i sidfoten. Beteendet beror på storleken på datauppsättningen på sidan. Om datauppsättningen är tillräckligt liten visas summorna automatiskt tillsammans med antalet rader i datauppsättningen. Om det finns bindestreck i sidfoten under de kolumner som du har konfigurerat för summor, är datauppsättningen för stor för systemet att visa summor omedelbart och en uttrycklig åtgärd krävs för att beräkna summorna. Det gör du genom att klicka på knappen **Beräkna** i sidfoten, eller högerklicka på en kolumn som du vill ha en summa för och välja **Summa den här kolumnen**.  

Om beräkningen tar för lång tid kan du avbryta operationen genom att välja knappen **Avbryt**. Ibland är datauppsättningen för stor för att beräkna summor (en begränsning som din organisation anger) och du ska istället bli meddelad om att filtrera data mer.

Summor uppdateras automatiskt när du uppdaterar, tar bort eller skapar rader i datauppsättningen.  

## <a name="grouping-data"></a>Gruppera data
Företagsanvändare behöver ofta för att utföra ad hoc-analys av data. Det kan du göra genom att exportera data till Microsoft Excel och med hjälp av pivottabeller och funktionen **gruppera** i tabellrutnät gör att användarna kan ordna sina data på intressanta sätt inom Finance and Operations-appar. När funktionen utökas kommer funktionen **Summor**, **Gruppera** också få meningsfulla insikter i data genom att tillhandahålla delsummor på gruppnivån.

Om du vill använda den här funktionen högerklickar du på den kolumn som du vill gruppera efter och väljer **gruppera efter denna kolumn**. Den här åtgärden sorterar data efter den markerade kolumnen, lägger till en ny grupp efter kolumn i början av rutnätet och infogar "rubrikrader" i början av varje grupp. Dessa rubrikrader innehåller följande information om varje grupp: 
-  Datavärde för gruppen 
-  Kolumnetikett (den här informationen är särskilt användbar när flera grupperingsnivåer stöds.)
-  Antal data rader i den här gruppen
-  Delsummor för alla kolumner som konfigurerats att visa summor

När [sparade vyer](saved-views.md) är aktiverad kan den här gruppen sparas med personlig anpassning som en del av en vy för snabbåtkomst nästa gång du besöker sidan.  

Om du väljer **gruppera efter denna kolumn** i en annan kolumn, ersätts den ursprungliga grupperingen eftersom det bara går att använda en grupperingsnivå i version 10.0.9 med plattformsuppdatering 33.

Om du vill ångra grupperingar i ett rutnät högerklickar du på grupperingskolumnen och väljer **Ta bort grupp**.  


## <a name="evaluating-math-expressions"></a>Utvärdera matematikuttryck
Som en produktivitetsförstärkning kan användarna ange matematiska formler i numeriska celler i ett rutnät. De behöver inte utföra beräkningen i en app utanför systemet. Om du till exempel anger **=15\*4** och tryck sedan på **Tabb** tangenten för att flytta ut ur fältet, utvärderas uttrycket och värdet **60** för fältet sparas.

Om du vill att ett värde ska identifieras som ett uttryck i systemet startar du värdet med ett likhetstecken (**=**). Mer information om operatorer och syntax som stöds finns i [matematiska symboler som stöds](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).  
