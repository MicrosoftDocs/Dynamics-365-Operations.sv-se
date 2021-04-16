---
title: Ställa in parametervärden för kostnadsredovisning
description: När du ställer in modulen för hemtagningskostnad kan du definiera flera uppsättningar med gemensamma värden som blir tillgängliga när du väljer specifika typer av kostnadsparametervärden i andra delar av programmet. Det här avsnittet beskriver hur du ställer in dessa uppsättningar med värden.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMCostTypeTable, ITMCostTypeGroup, ITMCostTransferGroup, ITMCostTemplateTable, ITMVolumetricDivisorTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 634635f7b751753033d1df8f56706b1e20479953
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841945"
---
# <a name="costing-parameter-values-setup"></a>Ställa in parametervärden för kostnadsredovisning

[!include [banner](../../includes/banner.md)]

När du ställer in modulen **Hemtagningskostnad** kan du definiera flera uppsättningar med gemensamma värden och relaterade inställningar per värde. Dessa värden kommer sedan att vara tillgängliga när du väljer specifika typer av kostnadsparametervärden i andra delar av programmet. Det här avsnittet beskriver hur du ställer in dessa uppsättningar med värden.

## <a name="set-up-cost-type-codes"></a>Ställa in kostnadstypkoder

Kostnadstypkoder avgör vilken typ av kostnad som uppstår när varorna landar på lagerstället, eller de hemtagningskostnader för lagerstället. Även om de vanligen ökar värdet på varorna kan de även användas för att periodisera belopp i redovisningen. Redovisningsjusteringar används när en kostnad periodiseras över en viss tid eller under en serie ändringar och motbokas i en enda transaktion.

> [!NOTE]
> Om kostnadstypsregistret delas av juridiska personer måste kontoplanen också delas mellan juridiska personer. Annars fungerar inte bokföringstransaktionerna korrekt.

Du ställer in dina kostnadstypkoder genom att gå till **Hemtagningskostnad \> Inställning av kostnadsredovisning \> Kostnadstypkoder**. Med knapparna i åtgärdsfönstret kan du skapa nya kostnadstypkoder, redigera befintliga koder eller ta bort en vald kostnadstyp.

Följande register beskriver de fält som är tillgängliga för varje kostnadstypkod.

| Fält | beskrivning |
|---|---|
| Kod för kostnadstyp | Ange ett namn för kostnadstypkoden. |
| beskrivning | Ange en beskrivning för kostnadstypkoden. |
| Använd leveranstariff | Ställ in det här alternativet till *Ja* om valutakursen för färden (kallas ibland för hanteringskurs) måste användas för att beräkna värdet på dessa kostnader. I detta fall används leveranskursen istället för standardvalutan eller punkttariffen för att växla fakturor i utländsk valuta. |
| Rapporteringskategori | Det här fältet gör en rapporteringskategori för kostnadstypen. Rapporter kan skrivas ut antingen efter rapportkategorier eller efter kostnadstyp. |
| Debettyp | Välj om kostnadstypen ska debitera artikeln, redovisningskontot eller leverantören. |
| Debetbokföring | Om fältet **Debettyp** anges till *Redovisningskonto* väljer du bokföringsbeskrivningen. |
| Debetkonto | Om fältet **Debettyp** anges till *Redovisningskonto* väljer du vilket redovisningskonto du ska använda. |
| Kredittyp | Välj om kostnadstypen ska kreditera artikeln, redovisningskontot eller leverantören. |
| Kreditbokföring | Om fältet **Kredittyp** anges till *Redovisningskonto* väljer du bokföringsbeskrivningen. |
| Kreditkonto | Om fältet **Kredittyp** anges till *Redovisningskonto* väljer du vilket redovisningskonto du ska använda. |
| Clearingkonto | Välj clearingkontot för kostnadstypen. Vi rekommenderar att du anger ett separat clearingkonto per kostnadstyp som hjälp vid avstämning. |
| Bokföringstypen standardkostnad | Om du använder standardkostnadsredovisning väljer du bokföringsbeskrivningen. |
| Belopp för standardkostnadsavvikelse | <p>Om du använder standardkostnadsredovisning används kontot som anges här för att bokföra eventuella avvikelser. I det här kontot används den landade kostnadsuppdelningen på sidan **Artikelpriser**. Uppdelningen skapas med den periodiska rutinen för att uppdatera priser.</p><p>Standardkostnaden för en artikel beräknas till $15,00, FOB beräknas $13,00 och frakten beräknas $2,00. När fakturan tas emot för lagret tas artikeln emot vid $15,00 men det finns en standardprisavvikelse $2,00 för artikeln, eftersom den faktiska FOB är $13,00. Den här avvikelsen bokförs på standard prisavvikelsekontot som ställs in i artikelbokföringsprofilen. Eftersom den uppskattade frakten $2,00 det inte finns någon avvikelse när lagerfakturan bokförs. När fakturan för frakt tas emot tas dock frakten $2,50 per enhet. Därför bokförs $0,50 avvikelse på den angivna kostnaden. |
| Glidande medelvärde för avvikelsekonto | <p>Om du använder kostnadsredovisning för rörligt genomsnitt används kontot som anges här för att bokföra eventuella avvikelser.</p><p>Den uppskattade frakten beräknas till $2,00. När fakturan för frakt tas emot tas dock frakten $2,50 per enhet. Därför måste $0,50 avvikelse bokföras.</p><p>När alternativet **Bokför justeringar som varians** anges till *Ja* på sidan **Parametrar för hemtagningskostnad** alla avvikelser mellan uppskattade och faktiska leveranskostnader kommer att bokföras till det avvikelsekonto för rörligt genomsnitt som anges här. När alternativet **Bokför justeringar som varians** anges till *Nej*, kommer standardfunktionen att användas och variansen appliceras antingen på lager eller avvikelsekonto för rörligt genomsnitt som anges här beroende på lagerbehållningen.</p> |
| Periodiseringskonto för avgift | Välj det konto som används för att periodisera för kostnadsuppskattningar när inköpsfakturan bokförs. Det här fältet används bara om alternativet **Använd periodiseringskonto för kostnadstyp** anges till *Ja* på snabbfliken **Kostnadsredovisning** på fliken **Allmänt** på sidan **Parametrar för hemtagningskostnad**. |
| Avgiftskonto | Välj det konto som används för att samla in de inkommande transportkostnaderna som har fakturerats av en leverantör. Beloppet bokförs som en debitering. Motkontot är kontot för lagervariationer. Denna bokföring används endast när alternativet **Bokför till debiteringskonto i redovisning** anges till *Ja* på sidan **Parametrar för leverantörsreskontra**. |
| Avvikelsekonto | Kontot som ska användas för att motboka debiteringsperiodiseringar när inköpsfakturan bokförs. Det här fältet används bara om alternativet **Använd periodiseringskonto för kostnadstyp** anges till *Ja* på snabbfliken **Kostnadsredovisning** på fliken **Allmänt** på sidan **Parametrar för hemtagningskostnad**. |

## <a name="vendor-cost-type-groups"></a>Kostnadstypsgrupper för leverantör

Kostnadstypgrupp för leverantör bestämmer hur avgifter för *automatisk kostnad* hittas och tillämpas på en färd. Leverantörer som har liknande importkostnader kopplas tillsammans. Alla leverantörer från dessa marknader betalar till exempel samma procentsats för samma typ av produkt som köps från en etablerad marknad.

Du kan underhålla kostnadstypgrupp för leverantör genom att gå till **Hemtagningskostnad \> Inställning av kostnadsredovisning \> Kostnadstypgrupp för leverantör**. Sidan **Kostnadstypgrupper för leverantör** tillhandahåller ett rutnät som listar alla befintliga kostnadstypgrupper för leverantör. Du kan använda knapparna i åtgärdsfönstret för att lägga till, ta bort och redigera rader i rutnätet.

Följande register beskriver de fält som är tillgängliga för varje rad i rutnätet.

| Fält | beskrivning |
|---|---|
| Kostnadstypsgrupper för leverantör | Ange ett unikt namn på leverantörskostnadsgruppen (t.ex. *tillväxtmarknader*). |
| beskrivning | Ange en beskrivning för kostnadstypgrupp för leverantör. Beskrivningen kan innehålla information om nivån eller typen av kostnad som associeras med leverantörsgruppen. |

## <a name="item-cost-type-groups"></a>Kostnadstypsgrupper för artikel

Kostnadstypgrupp för artikel bestämmer hur avgifter för *automatisk kostnad* hittas och tillämpas på en färd.. Liknande artiklar är kopplade till varandra. Till exempel kan alla artiklar som har en avgiftssats på 5 procent tillhöra en specifik kostnadstypgrupp.

Du kan underhålla kostnadstypgrupp för artikel genom att gå till **Hemtagningskostnad \> Inställning av kostnadsredovisning \> Kostnadstypgrupp för artikel**. Sidan **Kostnadstypgrupper för artikel** tillhandahåller ett rutnät som listar alla befintliga kostnadstypgrupper för artikel. Du kan använda knapparna i åtgärdsfönstret för att lägga till, ta bort och redigera rader i rutnätet.

Följande register beskriver de fält som är tillgängliga för varje rad i rutnätet.

| Fält | beskrivning |
|---|---|
| Kostnadstypsgrupper för artikel | Ange ett unikt namn på kostnadsgruppen för artikel (t.ex. *Avgift 5 %*). |
| beskrivning | Ange en beskrivning för kostnadstypgrupp för artikel. Beskrivningen kan innehålla information om nivån eller typen av kostnad som associeras med artikelgruppen. |

> [!NOTE]
> Artikelkostnadstypen är länkad till artikeln genom fältet **Kostnadstypgrupp** på snabbfliken **Inköp** på sidan **Frisläppt produkt**.

## <a name="transfer-order-cost-type-groups"></a>Kostnadstypgrupper för överföringsorder

Kostnadstypgrupper för överföringsorder bestämmer hur avgifter för *automatisk kostnad* hittas. Liknande artiklar är kopplade till varandra. Till exempel kan alla artiklar som har en avgiftssats på 7 procent tillhöra en specifik kostnadstypgrupp.

Du kan underhålla kostnadstypgrupper för överföringsorder genom att gå till **Hemtagningskostnad \> Inställning av kostnadsredovisning \> Överföringsorder, kostnadstypgrupper**. Sidan **Kostnadstypgrupper för överföringsorder** tillhandahåller ett rutnät som listar alla befintliga kostnadstypgrupper för överföringsorder. Du kan använda knapparna i åtgärdsfönstret för att lägga till, ta bort och redigera rader i rutnätet.

Följande register beskriver de inställningar som är tillgängliga för varje rad i rutnätet.

| Fält | beskrivning |
|---|---|
| Kostnadstypgrupper för överföringsorder | Ange ett unikt namn på kostnadstypgrupper för överföringsorder (t.ex. *Avgift 7 %*). |
| beskrivning | Ange en beskrivning för kostnadstypgrupper för överföringsorder. Beskrivningen kan innehålla information om nivån eller typen av kostnad som associeras med kostnadstypgrupper för överföringsorder. |

> [!NOTE]
> Kostnadstypgrupper för överföringsorder är länkad till artikeln genom fältet **Kostnadstypgrupper för överföringsorder** på snabbfliken **Inköp** på sidan **Frisläppt produkt**.

## <a name="cost-templates"></a>Kostnadsmallar

Du använder kostnadsmallar när du vill ange standardvärden för inställningar som användare som får kostnadsuppskattningen kanske inte vet. Kostnadsmallar minskar komplexiteten i uppskattningsprocessen genom att minimera de val som användarna måste ange för att få en korrekt uppskattning.

För att arbeta med kostnadsmallar, gå till **Hemtagningskostnad \> Inställning av kostnadsredovisning \> Kostnadsmallar**. På sidan **Kostnadsmallar** visas alla aktuella kostnadsmallar i listfönstret till vänster. Med knapparna i åtgärdsfönstret kan du lägga till, ta bort och redigera mallar.

Följande register beskriver de inställningar som är tillgängliga för varje mall.

| Fält | beskrivning |
|---|---|
| Kostnadsmall | Ange ett unikt namn för kostnadsmallen. Namnet beskriver vanligtvis faktorn eller kostnadsmultiplikatorn för mallen. |
| beskrivning | Ange en beskrivning för kostnadsmall. |
| Speditör | Välj leverantörskontot för rederiet som ska kopplas till kostnadsmallen. |
| Leveranssätt | Välj det leveranssätt som kostnadsmallen ska använda när den uppskattade kostnaden för en artikel beräknas. Det här fältet gör det lättare att bestämma de automatiska kostnader som associeras med varorna vid en kostnadsuppskattning. |
| Typ av fraktcontainer | Välj den typ av leveransbehållare som ska kopplas till kostnadsmallen. Det här fältet gör det lättare att bestämma de automatiska kostnader som associeras med varorna vid en kostnadsuppskattning. |
| Tullmäklare | Välj den tullmäklare (leverantör) som du vill koppla till kostnadsmallen. Det här fältet gör det lättare att bestämma de automatiska kostnader som associeras med en kostnadsuppskattning. |
| Faktor | Ange en faktor som ska användas för den slutliga kostnadsuppskattningen av varor. Skriv till exempel om du vill lägga till 10 procent till den beräknade kostnadsuppskattningen, ange *1,10*. |

## <a name="volumetric-divisors"></a>Volymavgränsare

Volymdelare används för att beräkna volymvikten. Varje leverans-/fraktföretag formulerar sina egna volymdelare. Dessutom varierar ett företags delare vanligtvis, beroende på leveranssättet. Till exempel har luft och hav ofta mycket olika delare. Ett företag kan också göra sina regler mer komplexa, beroende på varifrån det skickas.

Ett paket som skickas med flyg har till exempel en volym på 3 m³. Företagets avgifter per volymvikt och tillämpar en volymdelare på 6. Denna delare multipliceras med volymen för att bestämma volymvikten. Därför är volymvikten för det här exemplet 3 × 6 = 18 kilo (kg).

För att ställa in volymdelare, gå till **Hemtagningskostnad \> Inställning av kostnadsredovisning \> Volymdelare**. Sidan **Volymdelare** tillhandahåller ett rutnät som listar alla befintliga volymdelare. Du kan använda knapparna i åtgärdsfönstret för att lägga till, ta bort och redigera rader i rutnätet.

Följande register beskriver de fält som är tillgängliga för varje rad i rutnätet.

| Fält | beskrivning |
|---|---|
| Speditör | Välj leverantörskontot för rederiet som är associerat med volymdelaren. |
| Kod för kostnadstyp | Välj den kostnadstypkod som är associerad med volymdelaren. Använd det här fältet om du vill placera kostnadstyper i rapportgrupp. Rapporter kan skrivas ut antingen efter rapportkategorier eller efter kostnadstyp. |
| Från hamn | Välj den port "från" som volymdelaren gäller för. |
| Volymavgränsare | Ange det volymdelarens värde som gäller för raden. Värdet du anger *multipliceras* med volymen för varje paket för att bestämma paketets volymvikt. |
