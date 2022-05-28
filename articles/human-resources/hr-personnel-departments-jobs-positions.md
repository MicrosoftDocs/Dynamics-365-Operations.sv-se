---
title: Organisera personalen efter avdelningar, jobb och befattningar
description: Detta ämne beskriver konceptuell information som berör avdelningar, jobb och befattningar som utgör organisationselement som underhålls i Personal.
author: twheeloc
ms.date: 01/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 717bf7dcbd9a7e19a6dc960648655fdbd3e2465a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694835"
---
# <a name="organize-your-workforce-by-using-departments-jobs-and-positions"></a>Organisera personalen efter avdelningar, jobb och befattningar


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Avdelningar, jobb och befattningar är organisationselement som underhålls i Personal. Det här avsnittet beskriver begreppsmässig information om dessa element. 

Följande exempel används för att illustrera koncepten som beskrivs i det här avsnittet.

|**Avdelning**|**Befattning**|**Jobb**|
|---|---|---|
|**Försäljning**|Försäljningschef (öst)|Försäljningschef|
|**Försäljning**|Försäljningschef (väst)|Försäljningschef|
|**Försäljning**|Försäljningschef (central)|Försäljningschef|
|**Redovisning**|Redovisningsansvarig|Redovisningschef|
|**Redovisning**|Redovisning-A|Redovisare|
|**Personal**|Anställande chef (öst)|Anställande chef|
|**Personal**|Anställande chef (väst)|Anställande chef|
|**Personal**|Anställande chef (central)|Anställande chef|


##  <a name="departments"></a>Avdelningar

En avdelning är en driftenhet som representerar en kategori eller ett funktionellt område i organisationen, som är ansvarig för ett visst område i organisationen, till exempel försäljning eller redovisning. En avdelning används för att skapa rapporter om funktionella områden och kan ha vinst- och förlustansvar. En avdelning kan omfatta en grupp kostnadsställen. Försäljning, redovisning och personal är exempel på avdelningar i organisationen.

## <a name="jobs-and-positions"></a> Jobb och befattningar
Ett jobb är en samling uppgifter och ansvarsområden som krävs av en person, som utför ett jobb. En befattning är ett exempel på ett enskilt jobb. Ansvarsområden, jobbuppgifter, jobbfunktioner, information om färdigheter, intyg och utbildning som är obligatoriska för ett jobb, är också obligatoriska för befattningar som är kopplade till ett jobb.

### <a name="job-tasks"></a>Jobbuppgifter

Du kan skapa jobbuppgifter som beskriver grundläggande uppgifter, som en anställd i en befattning för det jobbet måste utföra. Samma jobbuppgift kan läggas till flera jobb och befattningar eftersom dessa jobb ärver jobbuppgifterna. Exempel på jobbuppgifter finns i följande tabell.

| Jobb           | Jobbuppgift                                                |
|---------------|-------------------------------------------------------------|
| Försäljningschef | Perf-granskning – Granska varje säljares jobbprestanda.    |
| Redovisare    | Abs-granskning – Godkänna eller avvisa varje säljares frånvaroförfrågningar eller registreringar. |


### <a name="job-functions"></a>Jobbfunktioner

Jobbfunktioner används på jobbuppgifter. En jobbfunktion beskriver en eller flera uppgifter eller ansvarsområden som tilldelats ett jobb. Jobbfunktioner kan tilldelas jobb och användas för att ställa in och implementera berättiganderegler för kompensationsplaner. Exempel på jobbfunktioner finns i följande tabell.

| Jobb           | Jobbfunktion                                                |
|---------------|-------------------------------------------------------------|
| Försäljningschef | Mng-personer – Hantera människor som rapporterar till dig.               |
| Redovisare    | FIN-granskning – Underhåll av ekonomiska data för en grupp konton. |

### <a name="job-types"></a>Jobbtyper

Använd jobbtyper för att klassificera liknande jobb i kategorier. Jobbtyåer, liksom jobbfunktioner, kan tilldelas jobb och användas för att ställa in och implementera berättiganderegler för kompensationsplaner. Exempel på jobbtyper anges i följande lista.
-   Heltid
-   Deltid
-   Lön
-   Timlön

### <a name="areas-of-responsibility"></a>Ansvarsområden

Använd ansvarsområden för att indikera arbetets roller, processer och produkter som en befattning för det jobbet skulle vara ansvarig för. Ett exempel på ett ansvarsområde för ett jobb som kallas "revisor" kan vara "Ekonomisk rapporteringen för produkt A”.

## <a name="positions"></a>Befattningar

Befattningar är ett viktigt element i den lägre nivån i en organisationshierarki. En befattning är ett exempel på ett enskilt jobb. Befattningen "Försäljningschef (öst)" är exempelvis bara en de befattningar som associeras med jobbet "Försäljningschef." Befattningar som finns på en avdelning och tilldelas arbetare.
### <a name="position-creation-and-maintenance"></a>Befattningskapelse och underhåll

-   Du kan visa en historik över befattningsrelaterade systemändringar på en lättillgänglig listsida.
-   Du kan skapa orsakskoder som användarna kan välja när de skapar och ändrar befattningar.
-   Du kan skapa typer av personalåtgärder och tilldela en nummerserie för personalåtgärder.
-   Du kan ställa in arbetsflöden, så att befattningtillägg och ändringar kan kräva godkännande.

### <a name="position-duration"></a>Befattningstidslängd
Varje befattning har en tidslängd som befattningen ska gälla. Den tidslängden kallas för varaktighet. Du kan till exempel ha sommarbefattningar med varaktighet 1 maj 2015 till 31 augusti 2015.

### <a name="worker-assignments"></a>Tilldelningar för arbetare
När du tilldelar en anställd till en befattning, fyller du den befattningen. Du kan tilldela flera anställda till befattningar, men bara en anställd kan tilldelas en befattning samtidigt.

### <a name="reporting-relationships"></a>Relationer till överordnad
Befattningar är ett viktigt element i den lägre nivån i en organisationshierarki. På sidan **Befattning** kan du ange den befattning som en befattning rapporterar till. När du tilldelar en anställd till en befattning som rapporterar till en annan befattning, skapar du en rapporteringrelation mellan arbetarna som tilldelas de två befattningarna. Till exempel rapporterar befattningen ”revisor-A” till befattning ”Redovisningschef". Anna Boman tilldelas befattningen ”Redovisningschef" och Felix Henriksson befattningen "Revisor-A”. Detta betyder att Felix Henriksson rapporter till Ana Enerman. 

Om din organisation använder en matrishierarki eller en annan anpassad hierarki, kan du ställa in befattninghierarkityper, och sedan lägga till rapporteringrelationer till befattningar för varje hierarkityp som du ställer in. Exempelvis är Olivia Nilsson chef på Adventure Works och tilldelas befattningen "Chef". Olivia leder utvecklingen av en produkt som används för att rena gränssnittskomponenter. Olivia kräver att en revisor hjälper henne med finanserna för att utveckla produkten. Därför har hon rekryterat Felix Henriksson som sin revisor. Felix rapporterar direkt till Anna Boman, men arbetar också tillsammans med Olivia Nilsson i sitt arbete som är relaterat till finanserna för att utveckla rengöringsmedlet för gränssnittskomponenter. 

För föregående exempel ska du utföra följande uppgifter om du vill ange arbetsrelationen mellan Felix Hendersson och Anna Boman:
1.  Skapa en anpassad befattningshierarkityp kallad Gränssnittskomponent” för att skapa en hierarki som inkluderar befattningar som ansvarar för arbete med gränssnittskomponentrengöringsmedelprodukten.
2.  Tilldela rbefattningen Chef att vara den befattning där befattningen Revisor-A rapporterar till i gränssnittskomponenthierarkin.

Använd sidan **Befattningshierarki** om du vill visa befattningarna rapporteringsstruktur. Om du har flera befattninghierarkier kan du visa hierarkin för varje enskild hierarki i **befattninghierarkin**. Du kan även söka efter en befattning efter befattnings-ID eller efter namnet på den arbetare som hör till befattningen. **Befattningshierarkin** är en organisationshierarki.

## <a name="date-effective-records"></a>Poster för giltighetsdatum
För alla poster kan du ange framtida ändringar i posten. Följande information är giltighetsdatum.

<table>
<thead>
<tr class="header">
<th>Poster</th>
<th>Anställningsdatum</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Jobb</td>
<td><ul>
<li>Detaljerad källinformation</li>
<li>Jobbklassificeringsinformation</li>
<li>Kompensationsinformation</li>
</ul></td>
</tr>
<tr class="even">
<td>Befattningar</td>
<td><ul>
<li>Detaljerad befattningsinformation</li>
<li>Tilldelningar för arbetare</li>
<li>Befattningstidslängder</li>
<li>Befattningshierarkier</li>
</ul></td>
</tr>
</tbody>
</table>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
