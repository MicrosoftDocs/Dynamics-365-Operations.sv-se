---
title: Kostnadskonfiguration för fördelad orderhantering (DOM)
description: I den här artikeln beskrivs kostnadskonfigurationen för fördelad orderhantering (DOM) i Dynamics 365 Commerce.
author: josaw1
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9aaff8f627adcd00be174a0b5f7bd398300cfef9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862030"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a>Kostnadskonfiguration för fördelad orderhantering (DOM)

[!include [banner](../includes/banner.md)]

Organisationer tar med flera kostnadskomponenter i beräkningen för att avgöra vilken plats som är bäst att uppfylla ordern från. Några av dessa kostnadskomponenter är leveranskostnad, hanteringskostnad och förpackningskostnad. Genom en kombination av dessa kostnader beräknas vilken plats som ska användas för uppfyllelse.

När den första iterationen av fördelad orderhantering (DOM) i Dynamics 365 Commerce optimerade tilldelningen av order för uppfyllelseplatser togs bara avståndet in i beräkningen. Även om avståndet kan korreleras mot kostnad, är det inte detsamma som kostnad. En leverans till nästa dag natten kostar till exempel mer än en tredagarsleverans eller sjudagarsleverans med samma avstånd.

Med funktionen för kostnadskonfiguration kan återförsäljare definiera och konfigurera ytterligare kostnadskomponenter som ska beräknas och tas hänsyn till när den bästa platsen att uppfylla orderrader fastställs.

När kostnadskomponenter konfigureras använder DOM-problemlösaren bara dessa kostnadsdefinitioner för att avgöra den bästa platsen för orderuppfyllande. Den tar inte hänsyn till avståndskomponenten som kostnad. Men om inga kostnadskomponenter har konfigurerats använder inte DOM-problemlösaren avståndskomponenten som en kostnad för att avgöra den bästa platsen för orderuppfyllande.

## <a name="set-up-cost-components"></a>Konfigurera kostnadskomponenter

Du kan definiera två huvudsakliga typer av kostnadskomponenter i systemet: **Leverans** och **Övrigt**.

Det går att använda flera beräkningsbaser för båda typerna av kostnadskomponenter, vilket visas i tabellen nedan.

<table>
<thead>
<tr>
<th>Typ av kostnadskomponent</th>
<th>Beräkningsbas</th>
</tr>
</thead>
<tbody>
<tr>
<td>Leverans</td>
<td>
<ul>
<li>Enkel</li>
<li>Nivåindelad</li>
</ul>
</td>
</tr>
<tr>
<td>Övrigt</td>
<td>
<ul>
<li>Försäljningsorder</li>
<li>Försäljningsrad</li>
<li>Plats</li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a>Kostnadskomponenttypen Leverans

Det här avsnittet innehåller information om hur du konfigurerar varje kombination av kostnadskomponenttypen **Leverans** och beräkningsbasen för leveranskostnader. Det innehåller också information om hur DOM-problemlösaren använder olika kombinationer.

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a>Kostnadskomponenttyp = Leverans och beräkningsbas = Enkel

Om en kombination kostnadskomponenttypen **Leverans** och beräkningsbasen **Enkel** används, baseras leveranskostnaden för ett leveranssätt antingen på en fast kostnad eller ett avstånd.

Du måste ställa in följande fält för den här kombinationen:

- **Kostnadsfaktor** – Ange en unik identifierare för kostnadsfaktorn.
- **Beskrivning** – Ange namnet och beskrivningen för kostnadsfaktorn.
- **Start datum** och **Slutdatum** – Med dessa fält kan du begränsa kostnadsfaktorn för ett specifikt datumintervall. Om du lämnar dessa fält tomma gäller kostnadsfaktorn för obestämd tid.
- **Aktiv** – Ange om kostnadsfaktorn är aktiv. DOM tar bara hänsyn till aktiva kostnadsfaktorer som är associerade till uppfyllelseprofilen.
- **Företag** – Ange den juridiska person som kostnadsfaktorn har konfigurerats för. Alla rader i beräkningskriterierna måste gälla för samma juridiska person.
- **Leveranssätt** – Ange de leveranssätt som kostnaden har konfigurerats för.
- **Beräkningstyp** – Ange hur kostnaden ska beräknas för ett specifikt leveranssätt. Det går att använda två beräkningstyper:

    - **Fast** – En fast kostnad används för leveranssättet. Om du väljer den här beräkningstypen definieras den fasta kostnaden med fältet **Kostnad**.
    - **Enhet för avstånd** – Kostnaden för leveranssättet beräknas som kostnadsvärdet som anges i fältet **Kostnad** multiplicerat med avståndet mellan leveransadressen och platserna.

- **Kostnad** – Ange det kostnadsvärde som används tillsammans med fältet **Beräkningstyp** för att beräkna kostnaden för ett leveranssätt.

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a>Kostnadskomponenttyp = Leverans och beräkningsbas = Nivåindelad

Om en kombination kostnadskomponenttypen **Leverans** och beräkningsbasen **Nivåindelad** används, baseras leveranskostnaden för ett leveranssätt antingen på en fast kostnad eller ett avstånd. I den här kombinationen baseras avståndet på ett nivåindelat intervall med avstånd.

Du måste ställa in följande fält för den här kombinationen:

- **Kostnadsfaktor** – Ange en unik identifierare för kostnadsfaktorn.
- **Beskrivning** – Ange namnet och beskrivningen för kostnadsfaktorn.
- **Standardkostnad** – Ange den kostnad som ska användas för ett leveranssätt om avståndet mellan leveransadressen och platsen inte ligger inom något av de nivåindelade avstånden för leveranssättet.
- **Start datum** och **Slutdatum** – Med dessa fält kan du begränsa kostnadsfaktorn för ett specifikt datumintervall. Om du lämnar dessa fält tomma gäller kostnadsfaktorn för obestämd tid.
- **Aktiv** – Ange om kostnadsfaktorn är aktiv. DOM tar bara hänsyn till aktiva kostnadsfaktorer som är associerade till uppfyllelseprofilen.
- **Företag** – Ange den juridiska person som kostnadsfaktorn har konfigurerats för. Alla rader i beräkningskriterierna måste gälla för samma juridiska person.
- **Leveranssätt** – Ange de leveranssätt som kostnaden har konfigurerats för.
- **Avståndstyp** – Ange om den nivåindelade avståndsdefinitionen är ett avstånd fågelvägen eller ett vägavstånd.
- **Avståndsenheter** – Ange enheten som det nivåindelade avståndet mäts i.
- **Avstånd från** – Ange startintervallet för det nivåindelade avståndet.
- **Avstånd till** – Ange slutintervallet för det nivåindelade avståndet.
- **Beräkningstyp** – Ange hur kostnaden ska beräknas för ett specifikt leveranssätt och det nivåindelade avståndet. Det går att använda två beräkningstyper:

    - **Fast** – En fast kostnad används för leveranssättet. Om du väljer den här beräkningstypen definieras den fasta kostnaden med fältet **Kostnad**.
    - **Enhet för avstånd** – Kostnaden för leveranssättet och det nivåindelade avståndet beräknas som kostnadsvärdet som anges i fältet **Kostnad** multiplicerat med avståndet mellan leveransadressen och platserna.

- **Kostnad** – Ange det kostnadsvärde som används tillsammans med fältet **Beräkningstyp** för att beräkna kostnaden för ett leveranssätt.

> [!NOTE]
> - När du definierar nivåindelade avstånd kontrollerar systemet att inga avstånd saknas eller överlappar.
> - Avståndstypen som används för ett leveranssätt måste vara densamma för alla nivåindelade avstånd.

### <a name="other-cost-component-type"></a>Kostnadskomponenttypen Övrigt

Det här avsnittet innehåller information om hur du konfigurerar varje kombination av kostnadskomponenttypen **Övrigt** och en annan kostnadstyp för kostnader som inte är leveranskostnader. Det innehåller också information om hur DOM-problemlösaren använder olika kombinationer.

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a>Kostnadskomponenttyp = Övrigt och Övrig kostnadstyp = Försäljningsorder

En kombination av kostnadskomponenttypen **Övrigt** och den övriga kostnadskomponenttypen **Försäljningsorder** används för att definiera kostnader på försäljningsordernivå som inte är leveranskostnader.

Du måste ställa in följande fält för den här kombinationen:

- **Kostnadsfaktor** – Ange en unik identifierare för kostnadsfaktorn.
- **Beskrivning** – Ange namnet och beskrivningen för kostnadsfaktorn.
- **Start datum** och **Slutdatum** – Med dessa fält kan du begränsa kostnadsfaktorn för ett specifikt datumintervall. Om du lämnar dessa fält tomma gäller kostnadsfaktorn för obestämd tid.
- **Aktiv** – Ange om kostnadsfaktorn är aktiv. DOM tar bara hänsyn till aktiva kostnadsfaktorer som är associerade till uppfyllelseprofilen.
- **Kostnad** – Ange kostnadsvärdet för en kostnad på försäljningsordernivå som inte är leveranskostnad.

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a>Kostnadskomponenttyp = Övrigt och Övrig kostnadstyp = Försäljningsrad

En kombination av kostnadskomponenttypen **Övrigt** och den övriga kostnadskomponenttypen **Försäljningsrad** används för att definiera kostnader på försäljningsorderradnivå som inte är leveranskostnader.

Du måste ställa in följande fält för den här kombinationen:

- **Kostnadsfaktor** – Ange en unik identifierare för kostnadsfaktorn.
- **Beskrivning** – Ange namnet och beskrivningen för kostnadsfaktorn.
- **Start datum** och **Slutdatum** – Med dessa fält kan du begränsa kostnadsfaktorn för ett specifikt datumintervall. Om du lämnar dessa fält tomma gäller kostnadsfaktorn för obestämd tid.
- **Aktiv** – Ange om kostnadsfaktorn är aktiv. DOM tar bara hänsyn till aktiva kostnadsfaktorer som är associerade till uppfyllelseprofilen.
- **Kostnad** – Ange kostnadsvärdet för en kostnad på försäljningsorderradnivå som inte är leveranskostnad.

#### <a name="cost-component-type--other-and-other-cost-type--location"></a>Kostnadskomponenttyp = Övrigt och Övrig kostnadstyp = Plats

En kombination av kostnadskomponenttypen **Övrigt** och den övriga kostnadskomponenttypen **Plats** används för att definiera kostnader som inte är leveranskostnader för en grupp med platser eller en enskild plats.

Du måste ställa in följande fält för den här kombinationen:

- **Kostnadsfaktor** – Ange en unik identifierare för kostnadsfaktorn.
- **Beskrivning** – Ange namnet och beskrivningen för kostnadsfaktorn.
- **Start datum** och **Slutdatum** – Med dessa fält kan du begränsa kostnadsfaktorn för ett specifikt datumintervall. Om du lämnar dessa fält tomma gäller kostnadsfaktorn för obestämd tid.
- **Aktiv** – Ange om kostnadsfaktorn är aktiv. DOM tar bara hänsyn till aktiva kostnadsfaktorer som är associerade till uppfyllelseprofilen.
- **Uppfyllelsegrupp** – Ange den grupp med platser som kostnaden som inte är en leveranskostnad definieras för.
- **Uppfyllelseplats** – Ange den plats som kostnaden som inte är en leveranskostnad definieras för.

    > [!NOTE]
    > Du kan inte ange en uppfyllelsegrupp och en uppfyllelseplats på samma rad för platsbaserade beräkningskriterier.

- **Kostnad** – Ange kostnadsvärdet för en kostnad som inte är leveranskostnad på uppfyllelsegruppnivå eller uppfyllelseplatsnivå.

> [!IMPORTANT]
> Om att DOM ska ta hänsyn till dessa kostnader under körning måste du lägga till kostnadsfaktorn i relevant uppfyllelseprofil.


[!INCLUDE[footer-include](../includes/footer-banner.md)]