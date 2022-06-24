---
title: Över-/undertransaktioner
description: Denna artikel innehåller information som hjälper dig att konfigurera information om principer för över-/undertransaktioner så att systemet kan bestämma hur överbearbetning och underbearbetning av varor ska hanteras vid inleverans.
author: Weijiesa
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMOverUnderTrans, ITMOverUnderToleranceTable, ITMOverUnderReasonTable, ITMOverUnderToleranceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 79ce18a462f9c2f93dceec82da7ee0209ab61f78
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845009"
---
# <a name="overunder-transactions"></a>Över-/undertransaktioner

[!include [banner](../../includes/banner.md)]

När beställningarna i en färd behandlas förväntar sig systemet att artikelkvantiteten som mottas i slutdestinationslagret för konsumtion ska matcha den kvantitet som anges på inköpsorderraderna som är associerade med färden. Eftersom den exakta kvantiteten på inköpsorderraderna inte alltid tas emot i lagret, kommer dock modulen **Hemtagningskostnad** definierar en uppsättning regler som används för att hantera övermottagande och undermottagande av varor. Dessa regler är särskilt viktiga eftersom den ursprungliga inköpsordern har fakturerats och inte längre kan ändras. Genom att konfigurera detaljerna för över/undertransaktionspolicyer aktiverar du systemet för att bestämma hur överbearbetning och underbearbetning av varor ska hanteras vid inleverans. Du kan också manuellt hantera över- och underlager genom att använda sidan **Över/undertransaktioner**.

## <a name="overunder-tolerances"></a>Över-/undertoleranser

Du anger toleranser för över- och underleverans om du vill ange över- och underkvantiteter eller volymer som kan bearbetas på en lagernivå utan att något fel uppstår. Om färdradinleveransen ligger utanför dessa toleranser måste den ändras och lösas innan raden kan stängas för vidare bearbetning.

Om du vill konfigurera toleranserna går du **Hemtagningskostnad \> Över/underinställning \> Över/undertoleranser**. Där kan du visa, redigera, lägga till och ta bort toleransposter. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Kontokod | <p>Definiera omfattningen av leverantörer som toleransen gäller för genom att välja ett av följande värden:</p><ul><li>**Register** – Över-/undertoleransen gäller bara för den leverantör som är vald för raden.</li><li>**Grupp** – Över-/undertoleransen gäller bara för alla leverantörer i leverantörens toleransgrupp som är vald för raden.</li><li>**Alla** – Över-/undertoleransen gäller alla leverantörer.</li></ul> |
| Kontorelation | Välj den leverantör eller leverantörsgrupp som över-/undertoleransen gäller för, beroende på vilket värde du har valt i fältet **Kontokod**. |
| Artikelkod | <p>Definiera omfattningen av artiklar som toleransen gäller för genom att välja ett av följande värden:</p><ul><li>**Register** – Över-/undertoleransen gäller bara för den artikel som är vald för raden.</li><li>**Grupp** – Över-/undertoleransen gäller bara för alla artiklar i artikelns toleransgrupp som är vald för raden.</li><li>**Alla** – Över-/undertoleransen gäller alla artiklar.</li></ul> |
| Artikelrelation | Välj den artikel eller artikelgrupp som över-/undertoleransen gäller för, beroende på vilket värde du har valt i fältet **Artikelkod**. |
| Beloppstolerans | Ange den beloppstolerans som ska användas för en hel inköpsorder. |
| Procenttolerans | Ange den procenttolerans som ska användas för en enskild inköpsorderrad. |

## <a name="overunder-reasons"></a>Över-/underorsaker

När en över- eller underkvantitet associeras med en mottagen rad kanske du måste identifiera orsaken till över- eller underkvantiteten. I detta fall kan du välja en orsak till över- eller underleverans på mottagningsraden när varorna tas emot.

Om du vill konfigurera över- och underleveransorsaker går du till **Hemtagningskostnad \> Över-/underinställning \> Över-/underorsaker**. Där kan du visa, redigera, lägga till och ta bort tillgängliga överleverans- och underleveransorsaker. Följande register beskriver de fält som är tillgängliga för varje orsak.

| Fält | beskrivning |
|---|---|
| Över-/underorsak | Ange ett unikt namn för orsaken till över- eller undermottagningstransaktionen. |
| beskrivning | Ange en beskrivning av över-/underorsaken. |
| Rörelse | Välj den rörelsejournal som är associerad med över-/underorsaken. Det här fältet visar en lista över alla tillgängliga journaler som journaltypen *Rörelse* är kopplad till på sidan **Lagerjournalnamn** (**Lagerhanteringsinställningar \> Journalnamn \> Lager**). |

## <a name="item-overunder-tolerance-groups"></a>Över-/undertoleransgrupper för artikel

Artiklar med liknande toleranser kan grupperas tillsammans. På detta sätt kan du ange över-/undertoleransen för alla artiklar i gruppen samtidigt.

För att konfigurera över-/undertoleransgrupper för artikel, gå till **Hemtagningskostnad \> Över-/underinställning \> Över-/undertoleransgrupper för artikel**. Där kan du visa, redigera, lägga till och ta bort poster för över-/undertoleransgrupper. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Över-/undertoleransgrupp | Ange ett unikt namn på gruppen. Välj ett namn som beskriver toleransen, till exempel *1 % Var*. |
| beskrivning | Ange en beskrivning för gruppen. |

## <a name="vendor-overunder-tolerance-groups"></a>Över-/undertoleransgrupper för leverantör

Du kan gruppera ihop leverantörer som regelbundet överleverans eller underleverans. Du kan sedan konfigurera över-/undertoleransen per grupp.

För att konfigurera över-/undertoleransgrupper för leverantör, gå till **Hemtagningskostnad \> Över-/underinställning för leverantör \> Över-/undertoleransgrupper**. Där kan du visa, redigera, lägga till och ta bort poster för över-/undertoleransgrupper. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Över-/undergrupper | Ange ett unikt namn på gruppen. Välj ett namn som beskriver typen av leverantörer som tillhör gruppen. |
| beskrivning | Ange en beskrivning för gruppen. |

## <a name="view-and-process-overunder-transactions"></a>Visa och bearbeta över-/undertransaktioner

Över- och undertransaktioner genereras när kvantiteten av varor som förs in inte matchar den initierade kvantiteten. Kvantiteten i införseljournalen bör bara uppdateras med den kvantitet som är införd.

När inleveransen av rader bearbetas kan du ange över-/undertoleranser för en leverantör. Artiklarna granskas och valideras sedan. Toleransen kan anges som en procentsats, ett lokalt belopp eller båda.

Om en artikel som införs finns i toleransen skapas en rörelsejournal i systemet. Den här journalen kan anges på parametersidan för färd. Dessutom skapas en över-/undertransaktion. Ordervärdet anges till exempel $100, inleveransvärdet anges $99 och dessa värden uppfyller toleransreglerna. I det här fallet skapas en negativ flyttningsjournal för den kvantitet som inte mottagits.

Om en artikel som in mottas ligger utanför toleransen genererar systemet en över-/undertransaktion för skillnaden i kvantitet.

Om du vill visa och bearbeta över-/undertransaktioner går du till **Hemtagningskostnad \> Förfrågningar \> Över/under-transaktioner**. Där kommer en över-/undertransaktion att associeras med alla artiklar i en transaktion som är övermottagen eller undermottagen. Vi rekommenderar att du använder sidan **Över-/undertransaktioner** för att lösa alla över-/undertransaktioner som är associerade med färder. Vi rekommenderar också att du **inte** använder förflyttningar eller inventeringsjournaler för att manuellt lösa lagertransaktioner för underleverans. I stället ska du använda sidan **Över-/undertransaktioner** för att hantera kvantiteterna för underleveranslagerstället.

### <a name="upper-overview-tab"></a>Övre fliken för översikt

Om du vill visa över-/undertransaktioner väljer du fliken **Översikt** i den övre delen av sidan **Över-/undertransaktioner**. Följande register beskriver de fält som är tillgängliga i rutnätet.

| Fält | beskrivning |
|---|---|
| Över-/undertransaktionsnummer | Det unika namnet på över-/undertransaktionsposten som automatiskt skapades när införseljournalen bearbetades. |
| Sjötransport | Den färd som inköpsraden var kopplad till. |
| Fraktcontainer | Den behållare som inköpsraden var kopplad till. |
| Införseljournal | Införseljournalen som över-/underraden genererades från. |
| Referens | En referens till inköpsordern eller överföringsordern som är associerad med över-/undertransaktionen. |
| Antal | Den inköpsorder som refereras i över-/undertransaktionen. |
| Leverantörskonto | Den leverantör som över- eller underleverantören är relaterad till. |
| Nummer för varor på väg | Numret för varor på väg, om det är tillämpligt. |
| Artikelnummer | Det artikelnummer som över- eller underleverantören är relaterad till. |
| Ursprunglig kvantitet | Den ursprungliga kvantiteten på inköpsorderraden som är kopplad till försändelsen. |
| Inlevererad kvantitet | Den kvantitet som faktiskt mottogs. |
| Differens | Skillnaden mellan beloppet för den förväntade införseljournalen och beloppet som bokfördes i införseljournalen. Ett negativt värde indikerar en överleverans av varor. |
| Återstående kvantitet | Den kvantitet som finns kvar på raden i införseljournalen. |
| Över-/underleverans | Ett värde som anger om den mottagna kvantiteten är en över- eller underkvantitet. |
| Status | Status för över-/undertransaktion. Beroende på inställningarna på sidan **[parametrar för hemtagningskostnad](landed-cost-parameters.md)** kan överleverans automatiskt skapa en rörelsejournal för överleveransbeloppet och bokföra journalen. I detta fall har över-/undertransaktionen statusen *Slutförd*. Om en åtgärd krävs för att flytta varorna från lagerstället för underleverans, får posten statusen *Pågår*. |
| Över-/underorsak | Orsaken som är associerad med över-/undertransaktionen. |
| Övriga lagerdimensioner | Du kan visa kolumner för ytterligare dimensioner i rutnätet om det behövs. Dimensionerna inkluderar batchnummer, lagerstatus och lagerställe. I åtgärdsfönstret, välj **Lager \> Visa dimensioner** om du vill öppna en dialogruta där du kan välja vilka dimensioner som ska ingå. |

### <a name="upper-general-tab"></a>Övre fliken Allmänt

Om du vill visa mer information om raden som för tillfället är markerad på den övre fliken **Översikt** väljer du fliken **Allmänt** i den övre delen av sidan **Över-/undertransaktioner**. Informationen på den här fliken omfattar värdena för alla tillgängliga dimensioner. Den här informationen hämtas från den ursprungliga inköpsordern.

### <a name="lower-overview-tab"></a>Nedre fliken för översikt

Om du vill visa dokumenttypen för raden som är markerad på den övre fliken **Översikt** väljer du fliken **Översikt** i den nedre delen av sidan **Över-/undertransaktioner**. Följande register beskriver de fält som är tillgängliga.

| Fält | beskrivning |
|---|---|
| Ny dokumenttyp | Det här fältet ställs in på antingen *Rörelsejournal* eller *Inköpsorder*, beroende på vilken åtgärd som visas på den valda över-/undertransaktionsraden. |
| Antal | En referens och länk till inköpsordern eller rörelsejournalen som är associerad med den valda över-/undertransaktionsraden. |
| Över-/underorsak | Orsaken som är associerad med den valda över-/undertransaktionsraden. |
| Kvantitet | Den kvantitet som du valde för inköpsordern eller rörelsejournalen som är associerad med den valda över-/undertransaktionsraden. |

### <a name="lower-general-tab"></a>Nedre fliken Allmänt

För att se över / under transaktionsnummer, parti-ID och dimensionsnummer som är associerade med den valda över-/undertransaktionsraden, välj fliken **Allmänt** på den nedre delen av sidan **Över-/undertransaktioner**. 

### <a name="process-overunder-transactions"></a>Bearbeta över-/undertransaktioner

Åtgärdsfönstret på sidan **över-/undertransaktioner** page tillhandahåller följande kommandon för bearbetning av de transaktioner som väljs på sidan. Varje kommando gör att du kan välja hur du vill bearbeta varje transaktion.

- **Skapa \> Rörelse** – Skapa och bokföra en rörelsejournal för den valda transaktionen. För undertransaktioner skapas en rörelsejournal automatiskt och bokförs för differensen mellan den förväntade och faktiska in mottagna kvantiteten. Välj det här kommandot för övertransaktioner om du vill att leverantören ska realisera kostnadsdifferensen.
- **Skapa \> Inköpsorder** – Skapa en inköpsorder för differensen mellan den förväntade och faktiska in mottagna kvantiteten för den valda transaktionen. Välj det här kommandot för övertransaktioner om din organisation vill realisera kostnadsdifferensen.
- **Skapa \> Överföring till destination** – Detta kommando gäller endast överföringsorder. Välj det om du vill överföra över- eller underkvantiteten till lagerstället vid destinationen.
- **Skapa \> Överföring till ursprung** – Detta kommando gäller endast överföringsorder. Välj det om du vill överföra över- eller underkvantiteten till ursprungliga lagerstället.
