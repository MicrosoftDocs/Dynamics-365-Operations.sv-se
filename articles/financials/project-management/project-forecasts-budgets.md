---
title: Projektprognoser och projektbudgetar
description: "Microsoft Dynamics 365 for Finance and Operations tillhandahåller projektprognoser och projektbudgetar för att hantera och kontrollera dina projekt."
author: KimANelson
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ForecastModel, ProjYearEndProcess
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23501
ms.assetid: 4e6d1384-19a2-4232-b3f3-d2590c218bd7
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: e31a013d6bf33b92b02bd9645a19380ba07f4a05
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="project-forecasts-and-budgets"></a>Projektprognoser och projektbudgetar

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 for Finance and Operations tillhandahåller två sätt för att hantera och kontrollera dina projekt: projektprognoser och projektbudgetar. 

Använda projektprognoser om organisationen har ett driftperspektiv och fokuserar på intäkter och kostnader som härleds från specifika transaktioner. Om din organisation fokuserar mer på ekonomiska belopp, kan du använda budgetering. 

Både projektprognoser och projektbudgetar använder prognosmodeller för att innehålla projekterade transaktionsbelopp. 

Varje metod har sina fördelar. Du bör beakta följande punkter innan du väljer en metod för din organisation.

|                           |                                          |                                                    |
|---------------------------|------------------------------------------|----------------------------------------------------|
|                           | **Projektprognoser**                  | **Projektbudgetar**                              |
| **Periodallokering**     | Du kan inte uttryckligen fördela transaktioner under en räkenskapsperiod. I stället baseras prognosen och kontrollen av prognosen på livslängden för projektet. Eftersom prognoser baseras på ett visst datum måste du härleda perioden från datumet. | Du kan fördela transaktioner över hela projektet eller en räkenskapsperiod. Om du fördelar över en period, kan du överföra oanvända belopp framåt till nästa räkenskapsperiod. |
| **Visa transaktioner**  | Du kan visa transaktioner i prognosformulären, där du ser prognoser för hela företaget och för alla projekt, oavsett hierarki. Fokusera på ett visst projekt genom att filtrera data.                                       | Du kan visa budgeterade transaktioner för en enskild projekthierarki. Därför kan du visa transaktionsdetaljer för ett överordnat projekt eller dess delprojekt.                 |
| **Transaktionsvariabler** | När du anger prognostransaktioner, kan du använda varje attribut som finns för en verklig transaktion. Detta möjliggör större noggrannhet i prognosen. Du kan till exempel ange information om kvantiteter, anställda, artiklar eller radegenskaper.         | När du anger budgetdetaljer, kan du endast använda belopp, kategorier och aktiviteter.                    |
| **Säkerhet**              | Prognoser bygger på transaktioner som du anger i prognosformulären och har ingen processtyrningsmekanism. Anställd som har behörighet till ett prognosformulär kan ändra information utan godkännande.                                        | Budgetering använder arbetsflödessystemet, som aktiverar ändringshantering och behåller en historik över ändringarna.         |
| **Inmatningstyper**           | Prognostransaktionsposter baseras på antalet enheter och på kostnads- och försäljningsenhetspriser.  | Budgetdetaljer baseras på belopp som delas upp mellan kostnader och intäkter.                                          |
| **Prognosmodeller**       | Eftersom varje prognos måste vara kopplad till en modell, kan du skapa flera prognosmodeller och även ställa in delmodeller.           | Projektbudgetar begränsar prognosmodellerna som används för budgeteringen. Färre prognosmodeller kan öka följdriktigheten i prognoser.                           |
| **Överskridna kostnader**         | Du kan endast tillåta eller förbjuda registrering av transaktioner som orsakar kostnadsöverskridande.   | Budgetering för projekt innehåller ytterligare kontrollalternativ för användare. Du kan tillåta varningar och överskridningar.                    |
| **Kontroll**               | Prognoskontroll utförs genom att använda prognosreducering. Verkliga belopp dras från prognostransaktionsaldon utan någon spårning. Detta kan göra det svårare att spåra var de verkliga transaktionerna uppstod.                   | I projektbudgetkontroll dras verkliga belopp från belopp i den resterande budgeten. Detta innebär en klarare spårning.                                   |

## <a name="project-forecasts"></a>Projektprognoser
När du använder projektberäkning, kan du ange prognostransaktioner i prognosformulär för varje transaktionstyp. Varje attribut som är tillgängligt för en verklig transaktion kan användas för en prognostransaktion, till exempel radlönsamhet, radattribut, arbetare eller beskrivningar. Du kan även projicera hur lång tid efter att en kostnad uppstår du fakturerar kunden. 

Projektberäkningstransaktioner baseras på enheter och belopp. 

Varje projektprognos måste vara kopplad till en prognosmodell. För varje prognostransaktion som registreras föreslås en prognosmodell automatiskt. Den prognosmodellen utgör en behållare för prognostransaktionerna. 

Du kan ställa in prognosmodeller som delmodeller för en modell. På så sätt kan du prognostisera efter region, tidsperiod eller avdelning. Du kan kopiera prognostransaktionerna i en modell för att skapa en ny modell och även överför också transaktionerna till redovisningen. Eftersom det finns en en-till-en-relation mellan en prognos och en modell utgör varje prognosmodell en separat budget för ett projekt. 

Prognosmodeller kan använda prognosförminskning som kontrollmekanism för projekt. Med prognosreducering minskar verkliga transaktioner prognostransaktionssaldon. Eftersom prognosförminskning tillämpas på det högsta projektet i hierarkin ger det en begränsad vy av ändringar i prognosen. Om till exempel en arbetstagare associeras med ett delprojekt, bokförs de verkliga transaktionerna för arbetstagaren i det överordnade projektet. Därför kan det vara svårt att spåra ändringar eftersom det inte är enkelt att avgöra vilken transaktion i vilket delprojekt som orsakade en reducering i prognosbeloppet. Därför är det en bra idé att skapa en kopia av en prognosmodell för att använda prognosreducering. Du kan sedan använda rapporter om du vill visa ursprunglig prognos. 

Projektprognoser kan ändras, kopieras, tas bort eller överföras till en redovisningsbudget. Det finns dock ingen processtyrning. Arbetare med behörighet till ett prognosformulär kan göra ändringar utan granskning.

-   **Ändra** – Du kan göra ändringar i en prognostransaktion i samma formulär där de ursprungliga posterna gjordes.
-   **Kopiera eller ta bort** – När du kopierar prognostransaktioner kopierar du transaktionsraderna i en prognosmodell till en annan prognosmodell. När du tar bort en prognos tar du bort prognostransaktionerna från en prognosmodell. Begränsa de prognostransaktioner som kopieras eller tas bort genom att välja specifika transaktionstyper och datum. På så sätt kan du kopiera eller ta bort endast vissa delar av en prognos.
-   **Överför** – När du överför en prognosbudget till en redovisningsbudget överför du prognostransaktionerna i en prognosmodell till en redovisningsbudget. Du kan skriva över alla tidigare överförda transaktioner i redovisningsbudgeten som du överför din projektprognos till.

## <a name="project-budgets"></a>Projektbudgetar
Budgetering för projekt är en enklare metod än prognoser men den kan integreras med prognosmodeller. Det använder ett enda formulär för information och ändringar för ursprunglig budget och tillåter projiceringar som baseras på endast belopp, kategori eller aktivitet. 

I projektbudgetering måste alla ursprungliga budgetar och ändringar skickas till ett projektarbetsflöde för godkännande. Arbetsflöden ger ökad kontroll över processerna och skapar en ändringshistorikpost. 

Budgetering för projekt liknar redovisningsbudgetering, men går snabbare och lättare att ställa in. Många av alternativen i redovisning såsom nummerserier eller valuta behöver inte ställas in separat för projekt.

Projektbudgeter associeras automatiskt med två prognosmodeller, en för ursprunglig budget och en för resterande budget. Därför kan rapporter baserade på prognosmodeller använda budgetdata. När en projektbudget disponeras skapar systemet prognostransaktioner som baseras på de kopplade modellerna, som används för rapportering och kontroll.

## <a name="forecast-models"></a>Prognosmodeller
Prognosmodeller har enskikts hierarki. Detta innebär att varje projektprognos måste vara kopplad till en prognosmodell.

Om du använder projektprognoser kan du identifiera modeller som delmodeller. Du kan sedan skapa prognoser efter avdelning, tidsperiod eller region. Du kan till exempel skapa en prognosmodell för ett år och sedan delmodeller för regionprognoserna nordost, sydost, nordväst och sydväst som regioncheferna skickar in. Genom att välja olika alternativ i det tillgängliga rapporterna kan du visa information efter total prognos eller efter delmodell.




