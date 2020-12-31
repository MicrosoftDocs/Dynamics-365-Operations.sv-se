---
title: Automatisering av inkassoprocess
description: I det här avsnittet beskrivs hur du ställer in processtrategier för inkasso som automatiskt identifierar kundfakturor som kräver en e-postpåminnelse, inkassoaktivitet (t.ex. ett telefonsamtal) eller ett kravbrev som ska skickas till kunden.
author: panolte
manager: AnnBe
ms.date: 08/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: db59bad2ed3caf38f22bd4d6059e57747d1d983f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447878"
---
# <a name="collections-process-automation"></a>Automatisering av inkassoprocess

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in processtrategier för inkasso som automatiskt identifierar kundfakturor som kräver en e-postpåminnelse, inkassoaktivitet (t.ex. ett telefonsamtal) eller ett kravbrev som ska skickas till kunden. 

Organisationer ägnar en lång tid på sig att undersöka föråldrade saldorapporter, kundkonton och öppna fakturor för att avgöra vilka kunder som måste kontaktas om en öppen faktura eller ett kontosaldo. Den här forskningen tar tid från en inkassohandläggare som används för att kommunicera med kunder för att samla in förfallna saldon eller lösa tvister om fakturan. Med automatisering av inkassoprocesser kan du ställa in ett strategibaserade tillvägagångssätt för din insamlingsprocess. På så sätt kan du utföra inkassoaktiviteter på ett konsekvent sätt genom att tillhandahålla anpassade e-postpåminnelser eller en programmerad process för sändning av kravbrev. 

## <a name="collections-process-setup"></a>Inställningar för insamlingsprocess
På sidan **Inställningar för insamlingsprocess** (**Kredit och inkasso > Inställningar > Inställningar för insamlingsprocess**) för att skapa en automatiserad inkassoprocess som schemalägger aktiviteter, skickar e-postmeddelanden och skapar och bokför kundkravbrev. Processtegen baseras på den första eller äldsta öppna fakturan. I varje steg används den här fakturan för att fastställa vilken kommunikation eller aktivitet som ska utföras med en viss kund.  

### <a name="process-hierarchy"></a>Processhierarki
Varje kundpool kan bara tilldelas en processmall. Rankningen av hierarkin för det här steget identifierar vilken process som ska prioriteras om en kund ingår i fler än en pool som har tilldelats en processmall. Pool-ID bestämmer vilka kunder som ska tilldelas processen. 

Tysta dagar används för att säkerställa att kunden inte kontaktas för ofta via den automatiska processen.  Om t.ex. tysta dagar är inställt på två kontaktas inte en kund av den automatiserade processen under minst två dagar, även om den ursprungliga inköpsfakturan har kvittats helt. 

Om du vill exkludera kunder från automatisering av processer om kontosaldot eller saldo är mindre än ett definierat värde ställer du in fältet **Exkludera från process** till **Ja** och anger sedan värdet för belopp.

## <a name="process-details"></a>Processdetaljer
**Beskrivning** används för att identifiera syfte eller namn på steget i hierarkin.

**Åtgärdstyp** definierar om steget ska skapa en aktivitet, skicka ett e-postmeddelande eller skapa ett kravbrev.

**Affärsdokument** definieras den mall som används för att skapa åtgärdstypen.  Det kan vara en aktivitetsmall, en e-postmall eller ett kravbrev per kund. 

Åtgärdstyperna kan skapas antingen före eller efter fakturans förfallodatum, baserat på den inställning som visas i **dagar i relation till kolumnen fakturans förfallodatum**.

När du väljer en e-poståtgärdstyp, används mottagaren för att definiera om det är en kontakt för kund, säljgrupp eller inkassohandläggare. Värdet i fältet **kontakt för arbetssyfte** kommer sedan avgöra vilken kontakt från kundkontot som ska ta emot kommunikationen.

## <a name="business-document-details"></a>Detaljer för affärsdokument
Detaljer för affärsdokument varierar beroende på vilken åtgärdstyp som har valts i processdetaljerna.  När åtgärdstypen är en aktivitet visas aktivitetsmallen information.  Informationen omfattar mallnamnet, den typ av aktivitet som skapas, syftet med aktiviteten, antalet schemalagda dagar som aktiviteten ska slutföras till och information om aktiviteten.  Denna aktivitet kommer sedan att länka till den inledande fakturan som talar om för mottagaren om vilken åtgärd som krävs för att slutföra aktiviteten.

Om åtgärdstypen är ett e-postmeddelande i processdetaljerna kommer det här avsnittet att innehålla två snabbflikar.  Den första används för att definiera mall-ID, e-postbeskrivning, standardspråk, användarnamnet som tilldelas e-postmeddelanden som skickas automatiskt och den associerade e-postadressen för avsändare. Det andra innebär att brödtexten i e-postmeddelandet skapas efter att värdena i fälten **språk** och **ämne** har sparats genom att välja **Redigera**.  Då öppnas ett fönster där HTML-innehållet kan överföras. Du kan också skriva det meddelande som skapas manuellt i den nedre vänstra rutan i fönstret.  

> [!Note]
> Ett e-postmeddelande i Outlook kan sparas med det önskade innehållet i kommunikationen i HTML-format. Detta kan sedan överföras för att implementera mallen. <br> <br> Om åtgärdstypen för kravbrev väljs, visas inte avsnittet affärsdokument information i inställningsformuläret.


## <a name="fasttab-reference"></a>Snabbfliken referens
I följande register visas de sidor och fält som de angivna snabbflikarna kan nås från, tillsammans med en beskrivning av informationen på fliken. 

### <a name="process-hierarchy"></a>Processhierarki

|     Sida                                                  |     Fält                         |     beskrivning                           |
| --------------------------------------------------------  |-------------------------------    |---------------------------------------    |
|     Inställningar för insamlingsprocess <br> Processautomatisering       |                                   |     Skapa och hantera inkassoprocesser baserat på tilldelningar av kundpooler.                                                                                                                             |
|     Inställningar för insamlingsprocess <br> Processautomatisering       |     Hierarki                     |     Definierar prioriteten för automatisering av processer för att tilldela en kund om den tillhör flera pooler.                                                                                                   |
|     Inställningar för insamlingsprocess <br> Processautomatisering       |     Pool-ID                       |     Frågor som definierar en grupp med kundposter.                                                                                                                                                        |
|     Inställningar för insamlingsprocess <br> Processautomatisering       |     Tysta dagar                    |     Begränsa hur ofta ett processteg kan slutföras. Om till exempel två tysta dagar har ställts in, kommer nästa steg i processen inte att inträffa i minst två dagar om den inledande fakturan ändras.     |
|     Inställningar för insamlingsprocess <br> Processautomatisering       |     Utelämna från process        |     Om du väljer antingen **balans mellan kundålder** eller **faktura beloppet mindre än** kommer att utesluta en kund från processautomatiseringen om värdekriterierna inte är uppfyllda.                                   |

### <a name="process-details"></a>Processdetaljer
|     Sida                                                  |     Fält                                         |      beskrivning                  |
|--------------------------------------------------------   |-----------------------------------------------    |----------------------------   |
|     Inställningar för insamlingsprocess <br> Processautomatisering       |                                                   |     Definiera de steg som vidtas utifrån den inledande fakturan.                                                                                                |
|                                                           |     beskrivning                                   |     Fritext fält som används för att ange ett namn och/eller en beskrivning av steget.                                                                           |
|                                                           |     Åtgärdstyp                                   |     Aktivitet, ett e-postmeddelande eller kravbrev som skapas av processteget.                                                                     |
|                                                           |     Affärsdokument                           |     Definierar aktivitets eller e-postmallen som används under processteget.                                                                        |
|                                                           |     När                                          |     Definierar om processteget ska inträffa före eller efter det inledande fakturans förfallodatum tillsammans med **dagarna i relation till fältet förfallodatum för faktura**.        |
|                                                           |     Dagar i relation till fakturans förfallodatum        |     Tillsammans med fältet **när** anger tidssteget för processteget.                                                                          |
|                                                           |     Mottagare                                     |     Anger om ett e-postmeddelande ska skickas till en kontaktperson för kund, säljgrupp eller inkasso.                                                   |
|                                                           |     Kontakt för affärssyfte                    |     Avgör vilken mottagares e-postadress som används i e-postkommunikationer.                                                                                 |

### <a name="business-process-activity-template-details"></a>Information om mallen affärsprocessaktivitet 
|     Sida                                                  |     Fält                     |      beskrivning                  |
|--------------------------------------------------------   |----------------------------   |-------------------------  |
|     Inställningar för insamlingsprocess <br> Processautomatisering       |                               |     Avsnitt i installationsprocessen som identifierar informationen i aktivitetsmallen.                                                                      |
|     Inställningar för insamlingsprocess <br> Processautomatisering       |     Aktivitetsmall       |     Identifierar typen, syftet, antalet dagar som ska slutföras och ger information om aktiviteten som kommer att skapas under ett steg i en aktivitetsprocess.       |

### <a name="business-document-email-template-details"></a>Information om e-postmallar för affärsdokument 
|     Sida                                                  |     Fält     |      beskrivning                  |
|--------------------------------------------------------   |-------------- |-----------------------------  |
|     Inställningar för insamlingsprocess <br> Processautomatisering       |               |     Identifierar e-postbeskrivningen, standardspråket, avsändaren och e-postadressen som skapas under ett steg i en e-postprocess.        |


### <a name="collections-history"></a>Inkassohistorik 
|     Sida                              |     Fält     |      beskrivning                                                          |
|------------------------------------   |-------------- |---------------------------------------------------------------------  |
|     Inställningar för insamlingsprocess       |               |     Visa den senaste historiken för den valda processhierarkin.     |

### <a name="collection-process-assignment"></a>Insamlingsprocessuppgift
|     Sida                              |     Fält     |      beskrivning                                                  |
|------------------------------------   |-------------- |-----------------------------------------------------------    |
|     Inställningar för insamlingsprocess       |               |     Visa kunder som har tilldelats en inkassoprocess.  
|     Manuell tilldelning               |               |     Visa kunder som har tilldelats en process manuellt eller välj vilka kunder som ska tilldelas en process. |
|     Förhandsgranska processtilldelning      |               |     Förhandsgranska de kunder som ska tilldelas en strategi när den körs.   |
|     Förhandsgranska kundtilldelning     |               |     Visa strategin som en viss kund är tilldelad.    |
 
### <a name="parameters"></a>Parameters
|     Sida                                                                  |     Fält                                             |      beskrivning                              |
|-------------------------------------------------------------------------- |------------------------------------------------------ |-------------------------------------  |
|     Parametrar för kundreskontra > automatisering av inkassoprocessen     |     Procentandel kunder per batchuppgift          |     Inställning för att bestämma antalet batchjobb per automatiseringsprocess.                                          |
|     Parametrar för kundreskontra > automatisering av inkassoprocessen     |     Bokför kravbrev automatiskt           |     För kravbrevs åtgärdstyper kommer brevet att bokföras under automationen.                                      |
|     Parametrar för kundreskontra > automatisering av inkassoprocessen     |     Skapa aktiviteter automatisering                |     Skapa och stäng aktiviteter för åtgärdstyper som inte är aktiviteter för att visa alla automatiserade steg som har vidtagits för ett konto.        |
|     Parametrar för kundreskontra > automatisering av inkassoprocessen     |     Antal dagar som insamling av inkassoprocesser ska fortsätta     |     Definierar antalet dagar som inkassohistoriken lagras.                                                       |
