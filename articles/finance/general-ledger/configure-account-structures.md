---
title: Konfigurera kontostrukturer
description: Den här artikeln innehåller information om kontostrukturer och ekonomiska dimensioner.
author: aprilolson
ms.date: 10/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: twheeloc
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b3fbdd6e2cac61c358848a21e1126bea900e86b2
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2022
ms.locfileid: "9713954"
---
# <a name="configure-account-structures"></a>Konfigurera kontostrukturer

[!include[banner](../includes/banner.md)]

Kontostrukturer använder huvudkonto och ekonomiska dimensioner för att skapa en uppsättning regler som bestämmer ordningen och värden som används för att ange kontonumret. Du kan skapa så många kontostrukturer som du behöver för ditt företag. Kontostrukturer tilldelas ett företags redovisningsinställningar så att de kan delas.

När du skapar en kontostruktur är det maximala antalet segment 11. Om du behöver fler än 11 segment än detta ska du noggrant utvärdera dina inställningar och krav, eftersom det påverkar användarupplevelsen. Överväg om ett segment kan erhållas i ett rapporterande scenario med en hierarki i stället för under datainmatning eller genom att använda ett användardefinierat fält. Om du vill rapportera på platsen, men du kan räkna ut plats genom avdelning eller kostnadsställe, skulle du inte behöva plats som en ekonomisk dimension. Om du efter utvärdering konstaterar att det behövs fler än 11 segment kan du lägga till ytterligare segment med hjälp av avancerade regler.

Kontostrukturer kräver huvudkontot. Huvudkontot behöver inte vara det första segmentet i strukturen och identifierar vilka kontostrukturen används under kontonummerposten. Därför kan värdet för huvudkontot bara finnas i en struktur som tilldelats redovisningen så att de inte överlappar. När kontostrukturen identifieras filtreras listan över tillåtna värden för att vägleda användaren genom plockning med endast giltiga värden, vilket minskar risken för fel i en journalpost.

> [!NOTE] 
> Om du planerar att budgetera mot en ekonomisk dimension måste den ingå i en kontostruktur. Budgetering använder för närvarande inte avancerade regler.

## <a name="example"></a>Exempel
För att illustrera den bästa metoden för att ställa in en kontostruktur, låt oss anta att ett företag vill spåra deras balansräkningskonton (100000..399999) på de ekonomiska dimensionsnivåerna konto och affärsenhet. För inkomst- och kostnadskonton (400000..999999) spårar de ekonomiska dimensioner, affärsenhet, avdelning och kostnadsställe. Om de gör en försäljning, vill de också följa upp kunden. Med det här scenariot skulle det rekommenderas att ha två kontostrukturer som är tilldelade till företagets redovisning – en för balansräkningskonton och en för resultatkonton. För att optimera användarupplevelse och validering bör kunden vara en avancerad regel som endast används när ett försäljningskonto används.

**Balansräkningskontostruktur**

|Huvudkonto          | Affärsenhet    |
|----------------------|-----------|
|100000..399999 | *;"&nbsp;"|

**Resultaträkningsstruktur**

|Huvudkonto          | Affärsenhet    |Avdelning          | Kostnadsställe    | &nbsp; |
|----------------------|------------------|--------------------|-----------|---|
|400000..999999 | \*;"&nbsp;"| \*;"&nbsp;"| \*;"&nbsp;"| \*;"&nbsp;"|

**Avancerad regel för att lägga till en kund**

Villkor: Om huvudkontot som ligger mellan 400000 och 499999, lägg till kund. Får inte vara tomt.

|Kund         |
|-----------------|
|\* |

I detta exempel är alla värden och tom tillåtna så \* och "&nbsp;" används.

## <a name="segments-and-allowed-values"></a>Segment och tillåtna värden
Avsnittet **Segment** och **Information om tillåtna värden** ger en rutnätsliknande upplevelse för att ange de regler som ska tillämpas på validering vid bokföring. Du kan skriva direkt i cellerna i rutnätet, importera dem från Excel eller använda avsnittet **Information om tillåtna värden** för att guida dig genom den.

Avsnittet **Information om tillåtna värden** hjälper dig att skapa villkor med hjälp av **operatorer** som börjar med, mellan, omfattar, och många andra.

[![Tillåta värden.](./media/account.png)](./media/account.png) 

Tillåtna värden används som standard på en journal- eller redovisningspostsida när det inte finns några andra möjliga värden att välja enligt kontostrukturinställningarna.

Här följer ett exempel på **Resultaträkningsstruktur**.

|Huvudkonto          | Affärsenhet    |Avdelning          | Kostnadsställe    |
|----------------------|-----------|----------------------|-----------|
|400000..999999 | 002 | 022 | 014 |

När du registrerar en journal och väljer ett konto i vinst- och förlustintervallet och väljer affärsenheten "002" kommer värdena 022 och 014 att vara standard i kontokontrollen. Det här beteendet kommer också att uppstå med sidan för redovisningsfördelning. 

## <a name="more-than-seven-criteria-needed"></a>Mer än sju villkor krävs

Du kan fortsätta lägga till dem på nästa rad om du har mer än sju villkor som behövs. Du märker att när du arbetar i avsnittet **Information om tillåtna värden** att villkoret **+Lägg till ny** inte längre är aktiv efter att det sjunde villkoret har angetts. Det beror på många faktorer såsom: 
 - Kolumnbredd 
 - Hur data lagras. 
 - Prestanda för kontrollen **Information om tillåtna värden**
 - Användbarhet  

> [!NOTE]
> En uppgradering från Microsoft Dynamics AX 2012 där fler än sju kriterier anges som inte stöds. Det måste korrigeras innan du slutför uppgraderingen till appar för ekonomi och drift. 

Om du vill fortsätta lägga till ytterligare villkor klickar du på **duplicera i segmentet** och **avsnittet tillåtna värden**. Kriterierna kommer att kopieras till en ny rad. Du kan sedan skriva över eller ändra avsnittet **Information om tillåtna värden**.

## <a name="best-practices"></a>Regelverk
När du ställer in dina kontostrukturer finns det metodtips som du kan följa. Detta är bara riktlinjer så att en holistisk diskussion om ditt företag, planering för tillväxt och underhållsplan bör betraktas som en del av denna diskussion.

- Kontrollera först huvudkontot eller så nära framför kontostrukturen som möjligt, så att användarna får den bästa guidade upplevelsen de kan under kontoposten.
  
  - Kontrollera att eventuella lösningar från tredje part som du tänker använda stöder huvudkontot på den första positionen.

- Återanvänd kontostrukturer så mycket som möjligt för att minimera underhåll över dina juridiska personer.

- Överväg att använda avancerade regler så att de kan återanvändas kontostrukturer variationer över juridiska personer.

- När du anger tillåtna värden, använd så mycket som möjligt intervall och jokertecken. Det inte bara möjligt att bygga och ändra utan underhåll, men systemet utför också bättre med den här konfigurationen.

- Placera inte bara en asterisk för varje segment i kontostrukturen och lita sedan endast på avancerade regler. Detta kan vara svårt att hantera och leder ofta fram till användarfel under underhåll som kan göra att systemet inte kan bokföras.

## <a name="account-structure-activation"></a>Aktivering av kontostruktur
När du är nöjd med dina nya inställningar eller en ändring av en kontostruktur måste du aktivera den. Om en kontostruktur tilldelas redovisningen kommer denna aktivering vara en tidskrävande process eftersom alla ej bokförda transaktioner i systemet måste vara synkroniserade med den nya strukturen. Bokförda transaktioner påverkas inte med hänsyn till förändringar struktur. Från och med programversion 10.0.31, finns en ny funktion med namnet **Prestandaförbättring för kontostrukturaktivering** i funktionshantering. Mer information om den här nya funktionen för aktivering av kontostruktur finns i [Prestandaförbättring för aktivering av kontostruktur](account-structure-improvement.md). 

Mer information finns i [planera din kontoplan](plan-chart-of-accounts.md), [ekonomiska dimensioner](financial-dimensions.md) och [och dimensionskombinationer (indelad kontroll) ange](enter-account-dimension-combinations-segmented-entry-control.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
