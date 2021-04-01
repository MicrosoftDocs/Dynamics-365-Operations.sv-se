---
title: Viktiga begrepp för inkassohantering
description: I avsnitten definieras viktiga begrepp för inkassohantering.
author: mikefalkner
manager: AnnBe
ms.date: 11/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7d71d436f561f0c9b0d8caef00191d1eb9b56580
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257692"
---
# <a name="collections-management-key-concepts"></a>Viktiga begrepp för inkassohantering

[!include [banner](../includes/banner.md)]

Innan du börjar ställa in eller arbeta med kassaavstämningar, ska du förstå följande begrepp:

- Ögonblicksbilder av åldersfördelningen för kunder innehåller information om åldersfördelade saldon vid en specifik tidpunkt.
- Inkassokundpooler hjälper dig att organisera arbetet.
- Inkassohandläggare kan ha sina egna kundpooler.
- Listsidor organiserar inkassokunder, aktiviteter och fall.
- All information om inkasso för en kund finns på sidan, och du kan vidta åtgärder från den sidan.
- Ränta och avgifter kan avfärdas, återinsättas eller återföras i ett steg.
- Avskrivningstransaktioner kan skapas i ett steg.
- NSF-transaktioner (otillräckliga medel) kan bearbetas i ett steg.

I det här avsnittet beskrivs varje begrepp.

## <a name="customer-aging-snapshots"></a>Ögonblicksbild av åldersfördelningen för kunder

En ögonblicksbild av åldersfördelning består av beräknade åldersfördelningssaldon för en kund vid en viss tidpunkt. Information om ögonblicksbilden av åldersfördelning visas på listsidan **Åldersfördelade saldon** och på sidan **Inkasso**. En ögonblicksbild av åldersfördelningen måste skapas innan du kan visa information på listsidorna för inkasso (**Åldersfördelade saldon**, **Inkassoaktiviteter** och **Inkassoärenden**).

För varje kund innehåller en ögonblicksbild av åldersfördelning en ögonblicksbild av åldersfördelning med rubrik och detaljposter som motsvarar varje åldersfördelningsperiod i åldersfördelningsperioddefinitionen.

Ögonblicksbild av åldersfördelninghuvudet innehåller totalt förfallet belopp, kreditgräns, följesedelbelopp, försäljningsorderbelopp, antalet omtvistade transaktioner och totalbelopp av de omtvistade transaktionerna för kundkontot. Alla öppna transaktioner för kunden inkluderas i beräkningen av dessa belopp. Det totala beloppet, kreditgränsen, följesedelbeloppet och försäljningsorderbeloppet visas i faktaboxen **Kreditinformation** på sidan **Inkasso**.

För varje åldersfördelningsperiod i åldersfördelningsperioddefinitionen skapas en ögonblicksbild av åldersfördelningdetaljpost. Varje ögonblicksbild innehåller åldersfördelningsperiod-ID och det totala beloppet för transaktioner med data som infaller under åldersfördelningsperioden. Transaktioner tilldelas en åldersfördelningsperiod, till exempel 30 dagar förfallen. Datumet är relativt till datumvärdet **Åldersfördelning som anges**, när du skapar ögonblicksbilden av åldersfördelning. Denna information visas på listsidorna **Åldersfördelade saldon** och i faktarutan **Åldersfördelade saldon** på sidan **Inkasso**.

## <a name="collections-customer-pools"></a> Kundinkassopooler 

Kundpooler är frågor som definierar en grupp med kundposter. Du kan använda dessa grupperade poster för att visa information om kundkontona som ingår och för att hantera inkasso eller åldersfördelningsprocesser för dem. Du kan använda kundpooler för att filtrera information på listsidan för inkasso. Du kan även använda dem för att filtrera de kundkonton som är inkluderade när ögonblicksbilder av åldersfördelning skapas.

## <a name="collections-agents"></a>Inkassohandläggare

Som standard kan användare visa all kundinformation på listsidorna för inkasso. Inkassohandläggareposter låter dig bestämma kundpoolerna som är använda för att filtrera information om listsidorna för Inkasso och sidan **Inkasso**.

Inkassohandläggare arbetar är en person som arbetar med kunder för att säkerställa att betalningarna samlas in i tid. De är arbetare som tilldelas till användare på sidan **Användarinställningar**.

## <a name="collections-list-pages"></a> Listsidor för Inkasso 

Följande listsidor hjälper dig att ordna information om inkasso:

- **Åldersfördelade saldon** – kolumnerna på listsidan visar kundsaldon och föråldrade belopp per åldersfördelningsperiod. Den här informationen lagras i en ögonblicksbild över åldersfördelningen. Åldersfördelningsperioderna bestäms av åldersfördelningsperioddefinitionen som används. Åldersfördelningsperioddefinitionen hämtas från kundpoolen, om en kundpool har angetts för poolfrågan. Om kundpoolen inte har någon åldersfördelningsperioddefinition används standardåldersfördelningsperioddefinitionen som angetts på sidan **Parametrar för kundreskontra**. Om ingen förvald definition av åldersfördelningsperioder har angetts används den första definitionen av åldersfördelningsperioder på sidan **Definitioner för åldersfördelningsperiod**.
- **Inkassoaktiviteter** – kolumnerna på listsidan visar aktiviteter som identifieras som inkassoaktiviteter. Dessa aktiviteter skapas, genom att använda sidan **Inkasso**. Använd aktiviteter för att spåra inkassorelaterat arbete som du gör.
- **Inkassoärenden** – kolumnerna på listsidan visar information om ärenden som har ärendekategori med ärendetypen **Inkasso**.

### <a name="aging-snapshots"></a>Ögonblicksbilder av åldersfördelningen

En ögonblicksbild av åldersfördelning måste skapas innan du kan visa information om listsidan Inkasso. Information visas bara för kunder som en ögonblicksbild av åldersfördelning har skapats för. De poster som visas på listsidan kan dessutom filtreras, enligt följande:

- Som standard har användare åtkomst till alla kunder som har en ögonblicksbild av åldersfördelning.
- Om kundpooler finns, måste en användare anges som en inkassohandläggare för att använda poolerna till att filtrera information om listsidorna för inkasso. Informationen begränsas till de kunder som ingår i den valda kundpoolen.
- Om en användare har ställts in som en inkassohandläggare, är endast poolerna som har valts för den inkassohandläggaren tillgängliga på listsidan för inkasso. Om alternativet **Tillåt handläggare att visa alla kundpooler** har valts på sidan **Inkassohandläggare** för inkassohandläggaren, är alla pooler tillgängliga för den handläggaren.

## <a name="collections-page"></a> Sidan Inkasso

Använd sidan **Inkasso** för att visa, hantera och vidta åtgärder om inkassoinformation, aktiviteter och ärenden för kunder.

Den övre delen av sidan visar ärenden för den valda kunden, i mittenavsnittet visas transaktioner för kunden och i det nedre avsnittet visas aktiviteter för kunden. Du kan skapa inkassoärenden för att spåra inkassoinformation för en eller flera transaktioner och aktiviteter. Informationen i det övre fönstret och lägre avsnitten kan filtreras efter fallet.

Faktaboxar visar åldersfördelade saldon och information om kreditgräns för valda kunden. Den här informationen lagras i en ögonblicksbild över åldersfördelningen. Om det behövs kan du uppdatera ögonblicksbilden av åldersfördelning med aktuell information.

Åtgärdsfönstret innehåller knappar som visar relaterad information för vald kund, ärende, transaktion eller aktivitet. Du kan också utföra vanliga åtgärder till exempel ändra inkassostatusen för en transaktion, skicka e-postmeddelande genom integration med din e-postleverantör, återbetalning till kunder, bearbetning och NSF-betalningar och avskrivning av saldon som inte kan inkasseras.

## <a name="waiving-reinstating-or-reversing-interest-and-fees"></a>Avfärda, återinsätta eller återföra ränta eller avgifter

Du kan efterskänka, återinföra eller återföra hela räntefakturor eller avgifter och transaktionränta som är en del av räntefakturor. Du kan göra detta från fliken **Inkasso** i åtgärdsfönstret på listsidan **Alla kunder** genom att klicka på **Räntefaktura**, **Transaktionsränta** eller **Avgift**.

Dessa justeringar påverkar endast räntefakturor, och ränta och avgifter som de innehåller. Mer information om hur du skriver av alla avgifter som en kund är skyldig finns i avsnittet [skapa avskrivningstransaktioner](#creating-write-off-transactions) i det här avsnittet.

Mer information finns i Skapa en räntekod med ett intervall och Bearbeta ränta.

## <a name="creating-write-off-transactions"></a>Skapa avskrivningstransaktioner

Du kan skriva av osäkra fordringar genom att välja **Skriv av** på sidan **Inkasso** och på listsidan för inkasso.

När du skriver av transaktioner för en kund, markeras alla transaktioner för kunden automatiskt för kvittning. Ett belopp, som skrivs av, beror på nettobeloppet för markerade transaktioner. Avskrivningstransaktionen skapas i en allmän journal och får innehålla maximalt tre typer av journalrader:

- Den första typen av journalrad innehåller kundavskrivningposten. Om markerade transaktioner innehåller flera kombinationer av valutakoder, dimensioner och bokföringsprofiler, skapas en separat journalrad för varje kombination.
- Den andra typen av journalrad innehåller redovisningsavskrivningsposten. Om markerade transaktioner innehåller flera kombinationer av valutakoder, dimensioner och bokföringsprofiler, skapas en separat journalrad för varje kombination.
- Den tredje typen av journalrad innehåller information för redovisningsavskrivning för moms. Denna journalrad skapas endast om alternativet **Separat moms** valts på sidan **Parametrar för kundreskontra**. Om markerade transaktioner innehåller flera kombinationer av konto för utgående moms, dimensioner och momskoder, skapas en separat journalrad för varje kombination. Avskrivningstransaktionen skapas i transaktionsvalutan. Mer information finns i Skapa en avskrivningsjournal för en kund.

## <a name="process-nsf-payments"></a>Bearbeta NSF-betalningar

Du kan bearbeta NSF-betalningar, genom att välja **NSF-betalning** på sidan **Inkasso**. När du klickar på den här knappen, annulleras betalningen. Om en NSF-avgift tillämpas för kunden, skapas en avgiftstransaktion i en betalningsjournal. Avgiftsbeloppet baseras på inställningarna för de automatiska avgifterna. De automatiska avgifterna som gäller för NSF-betalningar anges av avgiftsgruppen som valts på sidan **Bankkonton** för det berörda bankkontot.

## <a name="additional-resources"></a>Ytterligare resurser

[Inställningar för parametrar för kundkredithantering](./cm-credit-mgmt-setup.md)

[Inställningar för information för kundkredithantering](./cm-setup-information.md)

[Lägg till information för kredithantering för en kund](./cm-add-credit-mgmt-information-customer.md)

[Kreditgrupper för kund](./cm-customer-credit-groups.md)

[Justering av kundkreditgräns](./cm-credit-limit-adjustments.md)

[Kreditspärrar för försäljningsorder](./cm-sales-order-credit-holds.md)

[Periodiska kredithanteringsuppgifter för kund](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]