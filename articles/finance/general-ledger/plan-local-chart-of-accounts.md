---
title: Planera din lokala kontoplan
description: Det här ämnet innehåller information som hjälper dig att planera kontoplanen när du har krav på lagstadgade/lokala krav för din organisation.
author: VeselinaE
ms.date: 10/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts, LedgerConsolidateAccountGroup, MainAccountConsolidateAccount, DimensionDetails, MainAccountDetails
ROBOTS: ''
audience: Application User
ms.devlang: ''
ms.reviewer: twheeloc
ms.tgt_pltfrm: ''
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.search.industry: ''
ms.author: veneva
ms.search.validFrom: 10/07/2021
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 78379fd51cf24985fce83e2b6aa9a475af7df363
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946257"
---
# <a name="plan-your-local-chart-of-accounts"></a>Planera din lokala kontoplan

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information som hjälper dig att planera kontoplanen när din organisation innehåller juridiska personer som måste uppfylla kraven för specifika platser där de gör affärer. I den här artikeln beskrivs kontoplanerna med hjälp av följande termer:

- **Global** – Kontoplanen som organisationen använder globalt. I de flesta fall konsoliderar du den här kontoplanen.
- **Lokalt** – En kontoplan som juridiska personer i ett visst land eller en viss region använder.
- **Delad** – En kontoplan som mer än en juridisk person kan använda. Du kan dela både den globala kontoplanen och lokala kontodiagram.

Du kan skapa och dela flera kontoplanerna. En delad kontoplan kan användas av mer än en juridisk person, men bara en kontoplan kan tilldelas varje juridisk person. Kontoplanen som används av en juridisk person definieras på sidan **Redovisning**.

När de utformar kontoplanen är det många organisationer som siktar på en global kontoplan. Den delade kontoplanen gör det möjligt att skapa en global kontoplan. Det finns fördelar med att skapa och använda en enda kontoplan. Till exempel är styrning och kontroll, underhåll och rapportering enklare.

De flesta organisationer föredrar en global kontoplan, och det är enklast att implementera. Trots det kräver vissa juridiska personer en lokal kontoplan av följande skäl:

- Lokala lagstadgade krav
- Krav på lokala redovisningsstandarder
- Branschkrav
- Företagsspecifika rapporterings- och analysbehov

Om din organisation kräver att en juridisk person använder en lokal kontoplan finns det två alternativ tillgängliga för implementering av den:

- Tilldela den globala kontoplanen och definiera andra sätt att uppfylla de lokala kraven.
- Tilldela en lokal kontoplan till den juridiska personen, och definiera relationer till den globala kontoplanen.

Organisationsstrukturen och rapporteringsstrukturen bestämmer vilket alternativ som används.

[![Diagram som visar hur organisationsstrukturen avgör om en global eller lokal kontoplan ska användas](./media/local-chart-of-accounts-diagram.png)](./media/local-chart-of-accounts-diagram.png)

Om den globala kontoplanen tilldelas den juridiska personen finns följande alternativ tillgängliga för att uppfylla lokala rapporteringskrav:

- Gör lokal konsolidering.
- Använd en ekonomisk dimension när du vill spåra den lokala kontoplanen.
- Skapa lokala huvudkonton i den globala kontoplanen.
- Gör extern mappning till den lokala kontoplanen.

Om den lokala kontoplanen tilldelas den juridiska personen är global konsolidering det enda alternativet som är tillgängligt för att uppfylla globala rapporteringskrav.

## <a name="global-chart-of-accounts-assigned-to-a-legal-entity"></a>Global kontoplan som tilldelats en juridisk person

Om du måste tilldela den globala kontoplanen till en juridisk person finns det fyra alternativ för konfigurering av systemet, enligt beskrivningen ovan. För alla fyra alternativen konfigureras en enda kontoplan och länkas till varje juridisk person på sidan **redovisning**. Varje alternativ använder sedan ett annat sätt för att uppfylla lokaliseringskraven. Följande avsnitt beskriver stegen på hög nivå för att konfigurera systemet för lokaliseringskraven. De beskriver även fördelar och nackdelar med varje alternativ.

### <a name="do-local-consolidation"></a>Gör lokal konsolidering

Lokal konsolidering är det rekommenderade sättet att uppfylla lokala kontokrav och dra nytta av de systemfunktioner som har utformats för det här syftet.

#### <a name="set-up-consolidation-for-a-local-chart-of-accounts"></a>Ställ in konsolidering för en lokal kontoplan

1. Skapa en enda global kontoplan som omfattar alla nödvändiga huvudkonton.
2. I varje juridisk person tilldelar du den globala kontoplanen på sidan **redovisning**.
3. Skapa en juridisk konsolideringsenhet för varje lokalisering som krävs.
4. Gör något av följande:

    - Om bara en lokalisering krävs ska du konfigurera konsolideringskontot på sidan **Huvudkonto** eller använda sidorna **Konsolideringsgrupper** och **Ytterligare konsolideringskonton**.
    - Om mer än en lokalisering krävs, eller om både kontonumret och kontonamnet kräver översättning, använd sidorna **Konsolideringsgrupper** och **Ytterligare konsolideringskonton** för att representera lokaliseringskraven.

5. Kör konsolideringsprocessen om du vill transformera värdet från den juridiska personen som använder den globala kontoplanen till konsolideringsföretaget som använder den lokala kontoplanen.

#### <a name="advantages"></a>Fördelar

- Den här metoden ger ett konsekvent sätt att arbeta i hela organisationen.
- En översättning av den lokala befattningen görs.
- Det här arbetssättet stöder översättning av både huvudkonto-ID och namn för varje huvudkonto.
- Det stöder flera lokaliseringar.

#### <a name="disadvantages"></a>Nackdelar

- Ytterligare ett konsolideringsföretag skapas.
- Ytterligare en konsolideringsprocess har slutförts.
- Det här arbetssättet kan endast användas i det lokaliserade diagrammet när konsolideringsprocessen är klar.

### <a name="use-a-financial-dimension-to-track-the-local-chart-of-accounts"></a>Använd en ekonomisk dimension när du vill spåra den lokala kontoplanen

I det här sättet används en ekonomisk dimension där värdena för den ekonomiska dimensionen representerar de lokala huvudkonton som krävs för lokalisering. Det fungerar bra om endast en lokalisering krävs. Det blir dock mindre användbart när du lägger till fler lokaliseringar och ekonomiska dimensioner.

#### <a name="set-up-a-financial-dimension-for-a-local-chart-of-accounts"></a>Ställ in en ekonomisk dimension för en lokal kontoplan

1. Skapa en enda global kontoplan som omfattar alla nödvändiga huvudkonton.
2. I varje juridisk person tilldelar du den globala kontoplanen på sidan **redovisning**.
3. Skapa en ekonomisk dimension som representerar den lokala kontoplanen.
4. Skapa ekonomiska dimensionsvärden som representerar huvudkontona i den lokala kontoplanen.
5. Uppdatera kontostrukturen så att den innehåller den ekonomiska dimensionen "lokal kontoplan".
6. Se till att den ekonomiska dimensionen "lokal kontoplan" alltid har ett värde och att den inte tillåter något tomt värde. Överväg att använda härledda dimensioner eller fasta dimensioner.
7. Skapa en ekonomisk dimensionsuppsättning där den ekonomiska dimensionen "lokal kontoplan" är den första valda ekonomiska dimensionen. Den ekonomiska dimensionsuppsättningen kan användas när råbalansen genereras.

#### <a name="advantages"></a>Fördelar

- Huvudkontona i både globala och lokala kontodiagram finns på transaktionsnivå. Huvudkontot är globalt och värdet för den ekonomiska dimensionen är lokalt.
- Det här arbetssättet ger realtidsrapportering och vyer av både den globala finanspositionen och den lokala ekonomipositionen.

#### <a name="disadvantages"></a>Nackdelar

- Om redovisningsparametrarna för fältet **Värden som används för sammanfattningskonto** anges till **Redovisningsfördelningar**, de ekonomiska dimensionerna som representerar huvudkontot för utgiften/tillgången/intäkten kommer felaktigt att användas för konton för kundreskontra och leverantörsreskontra. Vi rekommenderar att du ställer in fältet till ett källdokument istället för att se till att rätt ekonomiska dimensionsvärden används.
- Om det krävs många lokala kontodiagram, och en ekonomisk dimension används för alla, kan listan med värden för den ekonomiska dimensionen som används bli lång och svår att arbeta med.
- Om det krävs många lokala kontoplan, och en separat ekonomisk dimension används för att representera var och en, kan systemets användarvänlighet och prestanda påverkas när ekonomiska dimensioner och ekonomiska dimensionsuppsättningar läggs till.
- Vi rekommenderar att du noggrant överväger antalet ekonomiska dimensioner som du behöver, antalet värden i var och en och antalet ekonomiska dimensionsuppsättningar, eftersom alla dessa faktorer kan påverka systemets prestanda.

### <a name="create-local-main-accounts-in-the-global-chart-of-accounts"></a>Skapa lokala huvudkonton i den globala kontoplanen

*Vad kopieringsredigerare frågade om:* I detta tillvägagångssätt inkluderar de lokala huvudkontona i den globala kontoplanen huvudkontona i den lokala kontoplanen i den globala kontoplanen.

*Ursprunglig version:* De lokala huvudkontona inom den globala CoA-metoden är att de lokala CoA-huvudkontona inkluderas i den globala CoA-redovisningskontona.

*Om det säger detta:* I detta tillvägagångssätt ingår de lokala huvudkontona i den lokala kontoplanen i den globala kontoplanen.


#### <a name="set-up-local-main-accounts-in-the-global-chart-of-accounts"></a>Ange lokala huvudkonton i den globala kontoplanen

1. Skapa en enda kontoplan som omfattar huvudkontona för både den globala kontoplanen och den lokala kontoplanen.
2. I varje juridisk person tilldelar du kontoplanen på sidan **redovisning**.
3. Skapa totala konton i kontoplanen för att summera huvudkontona som representerar samma syfte.
4. Skapa juridiska personer åsidosätter på varje lokalt konto för att förhindra transaktioner från andra juridiska personer som det lokala kontot inte har utformats för.
5. Skapa juridiska personer åsidosätter på varje globalt konto för att förhindra att transaktioner lokaliseras av juridiska personer.

#### <a name="advantages"></a>Fördelar

- En realtidsvy av både den globala finanspositionen och den lokala finanspositionen är tillgänglig på specifika rapporter och i specifika vyer i systemet, till exempel en balansräkningsrapport. Du öppnar det också genom att använda knappen **Period** i saldokontot.
- Det finns inget ytterligare segment i redovisningskontot.

#### <a name="disadvantages"></a>Nackdelar

- Saldokontots användning och synligheten är begränsade. Saldokonton visas till exempel inte på listsidan **Råbalans**.
- Underhållet kräver ytterligare arbete.
- Om du vill skapa ekonomiska rapporter måste du göra en manuell insats.

### <a name="do-external-mapping-to-the-local-chart-of-accounts"></a>Gör extern mappning till den lokala kontoplanen

En global kontoplan förutsätter att du hanterar mappning och lokalisering utanför systemet. I det här arbetssättet skapar du bara en enda global kontoplan i Microsoft Dynamics 365 Finance och hanterar behoven utanför systemet.

#### <a name="set-up-external-mapping-to-a-local-chart-of-accounts"></a>Ange extern mappning till den lokala kontoplanen

1. Skapa en enda global kontoplan som omfattar alla nödvändiga huvudkonton.
2. I varje juridisk person tilldelar du den globala kontoplanen på sidan **redovisning**.
3. Gör extern mappning till den lokala kontoplanen utanför Finance.

#### <a name="advantages"></a>Fördelar

- Den här metoden ger enhetliga sätt att arbeta i hela organisationen.

#### <a name="disadvantages"></a>Nackdelar

- Det finns ingen lokal rapportering från systemet.
- Den här metoden är benägen för fel när ekonomiska rapporter skapas.

## <a name="local-chart-of-accounts-assigned-to-legal-entity"></a>Lokal kontoplan som tilldelats en juridisk person

Om din organisation bestämmer sig för att inte använda en global kontoplan för flera juridiska personer, skapas en separat kontoplan för varje unik lokal kontoplan. Varje juridisk person länkas sedan till motsvarande kontoplan på sidan **Redovisning**.

### <a name="do-global-consolidation"></a>Gör global konsolidering

I den här metoden används ett konsolideringsföretag för att slå samman och kombinera saldona från varje lokalt källföretag till den kombinerade globala kontoplanen i konsolideringsföretaget. Den här metoden kräver att du underhåller en mappning av varje lokal kontoplan till den globala kontoplanen i konsolideringsföretaget.

#### <a name="set-up-global-consolidation"></a>Ange global konsolidering

1. Skapa en separat kontoplan för varje juridisk person som har olika lokala kontoplan. Om det finns juridiska personer som har samma lokala kontoplan krävs bara en lokal kontoplan och den kan delas.
2. I varje juridisk person tilldelar du lämplig kontoplan på sidan **redovisning**.
3. Valfritt: Skapa en kontoplan för den globala kontoplanen för varje konsolideringsföretag som har en annan global kontoplan.
4. Skapa en juridisk konsolideringsenhet för varje konsolideringsnivå som krävs, och tilldela lämplig kontoplan på sidan **redovisning**.
5. Gör något av följande:

    - Om endast en konsolidering krävs ska du konfigurera konsolideringskontot på sidan **Huvudkonto**.
    - Om mer än en konsolidering krävs, eller om både kontonumret och kontonamnet kräver översättning, använd sidorna **Konsolideringsgrupper** och **Ytterligare konsolideringskonton** för att representera kraven för globala kontoplaner.

6. Kör konsolideringsprocessen om du vill överföra saldon från de lokala juridiska personerna till den konsoliderade juridiska personen. Den här konsoliderade juridiska personen använder de konsolideringskonton som du definierade i steg 5.

#### <a name="advantages"></a>Fördelar

- Standardformatet för lokal redovisning används enhetligt.
- Det här arbetssättet gör det enklare för det lokala ekonomiteamet att arbeta.

#### <a name="disadvantages"></a>Nackdelar

- Det finns ingen tillgänglig realtidsvy av den globala positionen.
- Konsolideringsprocessen kan köras mer ofta.

## <a name="additional-resources"></a>Ytterligare resurser

- [Planera kontoplanen](plan-chart-of-accounts.md)
- [Konfigurera redovisningar](configure-ledger.md)
- [Ekonomiska dimensioner och bokföring](Default-dimensions.md#balancing-dimension)
- [Ekonomiska dimensionsuppsättningar](financial-dimension-sets.md)
- [Översikt över konsolidering och eliminering](../budgeting/consolidation-elimination-overview.md)
- [Konsolideringskontogrupper och ytterligare konsolideringskonton](../budgeting/consolidation-account-groups-consolidation-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
