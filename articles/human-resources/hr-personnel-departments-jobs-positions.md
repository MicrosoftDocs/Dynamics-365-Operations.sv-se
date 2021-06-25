---
title: Organisera arbetsstyrkan med hjälp av avdelningar, jobb och befattningar
description: Avdelningar, jobb och befattningar är organisationselement som underhålls i Personal. Det här avsnittet beskriver begreppsmässig information om dessa element.
author: andreabichsel
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 84e7017cb0bd799e27e19fc82009307d2955dea7
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189760"
---
# <a name="organize-your-workforce-by-using-departments-jobs-and-positions"></a>Organisera personalen efter avdelningar, jobb och befattningar

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

<table>
<thead>
<tr class="header">
<th>Jobb</th>
<th>Jobbuppgift</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Försäljningschef</td>
<td><ul>
<li><span class="input">Perf-granskning</span> – Granska varje säljares jobbprestanda.</li>
<li><span class="input">Abs-granskning</span> – Godkänna eller avvisa varje säljares frånvaroförfrågningar eller registreringar.</li>
</ul></td>
</tr>
<tr class="even">
<td>Redovisare</td>
<td><span class="input">FIN-rapport</span> – Aktuella veckovisa ekonomiska rapporter till ekonomichef.</td>
</tr>
</tbody>
</table>

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

Befattningar är ett viktigt element i den lägre nivån i en organisationshierarki. I formuläret Befattning kan du ange var en befattning som rapporterar till. När du tilldelar en anställd till en befattning som rapporterar till en annan befattning, skapar du en rapporteringrelation mellan arbetarna som tilldelas de två befattningarna. Till exempel rapporterar befattningen ”revisor-A” till befattning ”Redovisningschef". Kim Akers tilldelas befattningen ”Redovisningschef" och Sanjay Patel tilldelas befattningen "revisor-A”. Det innebär att Sanjay Patel rapporterar till Kim Akers. 

Om din organisation använder en matrishierarki eller en annan anpassad hierarki, kan du ställa in befattninghierarkityper, och sedan lägga till rapporteringrelationer till befattningar för varje hierarkityp som du ställer in. Exempelvis är Lori Penor chef på Adventure Works och tilldelas befattningen "Chef". Lori hanterar utvecklingen av en produkt som används för att rena gränssnittskomponenter. Lori kräver att en revisor hjälper henne med finanserna för att utveckla produkten. Därför hon har rekryterat Sanjay Patel för att vara hennes revisor. Sanjay rapporterar direkt till Kim Akers, men arbetar också med Lori Penor i dennes arbete som är relaterat till finanserna för att utveckla gränssnittskomponentrengöringsmedlet. 

För det tidigare exemplet ska du utföra följande uppgifter om du vill ange arbetsrelationen mellan Sanjay Patel och Lori Penor:
1.  Skapa en anpassad befattningshierarkityp kallad Gränssnittskomponent” för att skapa en hierarki som inkluderar befattningar som ansvarar för arbete med gränssnittskomponentrengöringsmedelprodukten.
2.  Tilldela rbefattningen Chef att vara den befattning där befattningen Revisor-A rapporterar till i gränssnittskomponenthierarkin.

Använd befattninghierarkin om du vill visa rapporteringstrukturen av befattningar. Om du har flera befattninghierarkier, kan du visa hierarkin för varje hierarki i befattninghierarkin. Du kan även söka efter en befattning efter befattnings-ID eller efter namnet på den arbetare som hör till befattningen. Befattninghierarkin är en organisationshierarki.

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

Du kan ändra informationen som nämns i tabellen ovan för en befattning eller ett jobb och ange ett datum, när ändringarna till befattningen eller jobbet ska genomföras. Till exempel kan en befattning endast tilldelas till en anställd, men Sanjay Patel, som är tilldelad befattningen Revisor-A lämnar den om två veckor. Joe Healy ska ersätta Sanjay Patel, när Sanjay lämnar. Även om Sanjay fortfarande tilldelas hans befattning, kan du tilldela Joe Healy till samma befattning så att tilldelningen är bara gäller efter Sanjays sista dag.







[!INCLUDE[footer-include](../includes/footer-banner.md)]