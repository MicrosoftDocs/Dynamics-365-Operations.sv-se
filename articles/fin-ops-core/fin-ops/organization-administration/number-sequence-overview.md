---
title: Nummerserier – översikt
description: Nummerserier används för att generera läsliga unika identifierare för huvuddataposter och transaktionsposter och som kräver identifierare.
author: SunilGarg
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceConfiguration
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom:
- "15461"
- intro-internal
ms.assetid: 6e19bd1d-192b-4da2-8573-84f6e1ce98ef
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 48e395cc3e3ccd0f93ab9523add455ef16f612ba
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985691"
---
# <a name="number-sequences-overview"></a>Nummerserier – översikt

[!include [banner](../includes/banner.md)]

Nummerserier används för att generera läsliga unika identifierare för huvuddataposter och transaktionsposter och som kräver identifierare. En huvuddatapost eller en transaktionspost som kräver en identifierare kallas för en *referens*.

Innan du kan skapa nya poster för en referens, måste du ställa in en nummerserie och koppla den till referensen. Vi rekommenderar att du använder sidorna i **Organisationsadministration** för att ställa in nummerserier. Om modulspecifika inställningar krävs kan du använda parametersidan i en modul för att ange nummerserier för referenserna i den modulen. I **Kundreskontra** och **Leverantörsreskontra** kan du till exempel ställa in nummerseriegrupper för att allokera specifika nummerserier till vissa kunder eller leverantörer.

När du anger en nummerserie, måste du ange omfång, som definierar vilken organisation som använder nummerserien. Omfånget kan vara **Delat**, **Företag**, **Juridisk person** eller **Driftenhet**. Omfattningarna **Juridisk person** och **Företag** kan kombineras med **Räkenskapskalenderperiod** för att skapa ännu mer specifika nummerserier.

Nummerserieformat består av segment. Nummerserier som har ett annat omfång än **Delat** kan innehålla segment som motsvarar omfånget. Till exempel kan en nummerserie med omfånget **Juridisk person** innehålla ett segment med en juridisk person. Genom att inkludera ett omfångsegment i nummerserieformatet kan du identifiera omfånget för en viss post med hjälp av numret.

Förutom segment som motsvarar omfång kan nummerserieformat innehålla **konstanta** och **alfanumeriska segment**. Ett **konstant** segment innehåller en uppsättning bokstäver, siffror eller symboler som inte ändras. Ett **alfanumeriskt** segment innehåller en uppsättning bokstäver eller siffror som ökar varje gång ett nummer används. Använd ett nummertecken (\#) om du vill ange ökande nummer och ett et-tecken (&) om du vill ange att ökande bokstäver. Med formatet \#\#\#\#\#\_2017 skapas till exempel serien 00001\_2017, 00002\_2017, och så vidare.

## <a name="number-sequence-examples"></a>Exempel på nummerserier

Följande exempel visar hur du använder segment när du vill skapa nummerserieformat. Närmare bestämt visar exemplen effekterna av att använda omfångsegment.

### <a name="expense-report-numbers"></a>Utgiftsrapportnummer

I följande exempel ställs utgiftsrapportnummer in för den juridiska personen med namnet **CS**.

- **Område:** Resor och utgifter
- **Referens:** Rapportnummer för utgifter
- **Omfång:** Juridisk person
- **Juridisk person:** CS

| Segment  | Segmenttyp | Värde     |
|-----------|--------------|-----------|
| Segment 1 | Juridisk person | CS        |
| Segment 2 | Konstant     | -UTGIFT- |
| Segment 3 | Alfanumerisk | \#\#\#\#  |

**Exempel på formaterat nummer**: CS-UTGIFT-0039

Du kan ställa in ett liknande nummersekvensformat för andra juridiska personer. Om du bara ändrar värdet för segmentet med en juridisk person, **RW**, är det formaterade numret RW-EXPENSE-0039, till exempel. Du kan också ändra heltalsekvensformatet för andra juridiska personer. Du kan till exempel utesluta ett segment med ett omfång av juridiska personer om du vill skapa ett formaterat nummer, som Exp-0001.

### <a name="sales-order-numbers"></a>Försäljningsordernummer

I följande exempel ställts försäljningsordernummer in för företags-ID **CEU**.

- **Område:** Försäljning
- **Referens:** Försäljningsorder
- **Omfång:** Företag
- **Företag:** CEU

| Segment  | Segmenttyp | Värde    |
|-----------|--------------|----------|
| Segment 1 | Konstant     | SO-      |
| Segment 2 | Alfanumerisk | \#\#\#\# |

**Exempel på formaterat nummer**: SO-0029

Även om ett omfångssegment inte ingår i formatet ska numreringen börja om för varje företags-ID. Om du använder samma format för alla företags-ID:n, används samma nummer i varje företag. Försäljningsordernumret SO-0029 används till exempel på varje företag. Du kan också ändra heltalsekvensformatet för andra företags-ID:n.

### <a name="purchase-requisition-numbers"></a>Inköpsrekvisitionsnummer

I följande exempel ordnas inköpsrekvisitionsnummer på företagsnivå.

- **Område:** Inköp
- **Referens:** Inköpsrekvisition
- **Omfång:** Delat

| Segment  | Segmenttyp | Värde    |
|-----------|--------------|----------|
| Segment 1 | Konstant     | Req      |
| Segment 2 | Alfanumerisk | \#\#\#\# |

**Exempel på formaterat nummer**: Req0052

Eftersom omfånget är **Shared** används nummerserieformatet i hela organisationen. Du kan inte ställa in olika nummerserieformat för olika delar av organisationen.

## <a name="performance-considerations-for-number-sequences"></a>Prestandaöverväganden för nummerserier

Beakta följande information om hur konfigurationen av nummerserier kan påverka systemets prestanda innan du ställer in nummerserier.

### <a name="continuous-and-non-continuous-number-sequences"></a>Kontinuerliga och icke-kontinuerliga nummerserier

Nummerserier kan vara kontinuerliga eller icke-kontinuerliga. En kontinuerlig nummerserie hoppar inte över något nummer, men numren kan inte användas i följd. Nummer från en icke-kontinuerlig nummerserie används efter varandra, men nummerserien kan hoppa över nummer. Om till exempel en användare annullerar en transaktion, genereras ett nummer men det används inte. I en kontinuerlig nummerserie återanvänds det numret senare. I en icke-kontinuerlig nummersekvens används inte numret.

Kontinuerliga nummerserier krävs vanligtvis för externa dokument, till exempel inköpsorder, försäljningsorder och fakturor. Kontinuerliga nummerserier kan dock påverka systemsvarstiderna negativt eftersom systemet måste begära ett nummer från databasen varje gång som ett nytt dokument eller en ny post skapas.

Om du använder en icke-kontinuerlig nummersekvens kan du aktivera **Förallokering** på snabbfliken **Prestanda** på sidan **Nummersekvenser**. När du anger ett antal nummer för förallokering väljer systemet de siffrorna och lagrar dem i minnet. Nya nummer krävs från databasen enbart efter att den förallokerade kvantiteten har använts.

Om det finns ett reglerat krav där du använder kontinuerliga nummerserier, rekommenderar vi att du använder icke-kontinuerliga nummerserier för bättre prestanda.

### <a name="automatic-cleanup-of-number-sequences"></a>Automatisk rensning av nummerserier

I händelse av strömavbrott, programfel eller annat oväntat fel kan inte systemet återanvända nummer automatiskt för kontinuerliga nummerserier. Du kan köra rensningen manuellt eller automatiskt återställa de förlorade numren.

Tänk noggrant igenom serveranvändningen när du planerar rensningen. Vi rekommenderar att du utför rensningen som ett batchjobb under tider då arbetsbelastningen är låg.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
