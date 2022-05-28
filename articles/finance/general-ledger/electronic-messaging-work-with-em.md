---
title: Arbeta med funktioner för elektroniska meddelanden
description: I detta ämne finns information om hur du arbetar med funktionen för elektroniska meddelanden (EM).
author: liza-golub
ms.date: 07/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a65971fa1da60b00bb525d450c0eb59aee57116e
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2022
ms.locfileid: "8733775"
---
# <a name="work-with-the-electronic-messages-functionality"></a>Arbeta med funktioner för elektroniska meddelanden

[!include [banner](../includes/banner.md)]

Om du arbetar på meddelandenivån är sidan **elektroniska meddelanden** (**Skatt** \> **förfrågningar och rapporter** \> **elektroniska meddelanden** \> **elektroniska meddelanden**)mer användbar. Om du arbetar på datainsamlings- eller meddelandeobjektnivå är sidan **Elektroniska meddelanden** (**Skatt** \> **Förfrågningar och rapporter** \> **Elektroniska meddelanden** \> **Elektroniska meddelanden**) mer praktisk.

## <a name="electronic-messages"></a>Elektroniska meddelanden

Sidan **elektroniska meddelanden** visar den behandling som är tillgänglig för dig, baserat på din roll. Säkerhetsroller är kopplade till bearbetning i inställningarna för bearbetning. För varje bearbetning som är tillgänglig för dig visar sidan elektroniska meddelanden och information som är relaterad till dem.

Snabbfliken **Meddelanden** visar elektroniska meddelanden för det valda jobbet. Beroende på status för det valda meddelandet och fördefinierad behandling kan du köra vissa åtgärder genom att välja knapparna ovanför rutnätet:

- **Ny** – den här knappen är kopplad till åtgärder i typen **Skapa meddelanden**.
- **Ta bort** – Denna knappen är tillgänglig om kryssrutan **Tillåt borttagning** är markerad för aktuell status för det markerade meddelandet.
- **Samla in data** – Den här knappen är kopplad till en åtgärd av typen **fylla i poster**.
- **Generera rapport** – den här knappen är kopplad till åtgärder av typen **Meddelande om export av elektronisk rapportering**.
- **Skicka rapport** – den här knappen är kopplad till åtgärder av typen **webbtjänst**.
- **Importera svar** – den här knappen är kopplad till åtgärder av typen **Import av elektronisk rapportering**.
- **Uppdatera status** – den här knappen är kopplad till åtgärder av typen **Användares bearbetning på meddelandenivå**.
- **Meddelandeartiklar** – öppnar sidan **Elektroniska meddelandeartiklar**.

Snabbfliken **Åtgärdslogg** visar information om alla åtgärder som har körts för det markerade meddelandet. Om en åtgärd resulterade i ett fel, ska information om felet bifogas till relaterad rad i rutnätet. Om du vill granska information om felet markerar du raden i rutnätet och väljer sedan knappen **Bilaga** (gemsymbolen) i det övre högra hörnet på sidan.

Snabbfliken **Ytterligare fält för meddelande** visar alla ytterligare fält som har definierats för meddelanden i inställningarna för bearbetning. Snabbfliken innehåller även värdena för dessa ytterligare fält.

Snabbfliken **Meddelandeobjekt** visar alla meddelandeobjekt som är relaterade till det markerade meddelandet. Beroende på status för den valda meddelandeartikeln kan du köra vissa åtgärder genom att välja knapparna ovanför rutnätet:

- **Ta bort** – Denna knapp är tillgänglig om kryssrutan **Tillåt borttagning** är markerad för aktuell status för den markerade meddelandeartikeln.
- **Uppdatera status** – den här knappen är kopplad till åtgärder av typen **Användarbearbetning**.
- Välj **originaldokumentet** – Öppna en sida som visar det ursprungliga dokumentet för den markerade meddelandeartikeln.

De rapporter som redan har skapats och mottagits för ett meddelande är kopplade till det meddelandet. Om du vill granska bilagor relaterade till ett meddelande markerar du meddelandet och väljer sedan knappen **Bilaga** (gemsymbolen) i det övre högra hörnet på sidan.

![Knappen Bilaga](media/attachment-icon.png)

Sidan **Bilagor** visar de bilagor som hör till det valda meddelandet. Om du vill visa en fil markerar du den i listan till vänster och markerar sedan **Öppna** i åtgärdsfönstret.

![Knappen Öppna](media/open-button.png)

Du kan granska bilagor som hör till en viss åtgärd som kördes tidigare för ett meddelande. Välj meddelandet på sidan **Elektroniska meddelanden** > snabbfliken **Meddelanden**. På snabbfliken **Åtgärdslogg** väljer du åtgärden och sedan knappen **Bilaga** (gemsymbolen) i sidans övre högra hörn.

Du kan också köra hela bearbetningen eller bara någon specifik åtgärd genom att markera **Kör bearbetning** i åtgärdsfönstret.

## <a name="electronic-message-items"></a>Elektroniska meddelandeartiklar

Sidan **Elektroniska meddelandeartiklar** visar alla meddelandeobjekt och en logg över de åtgärder som har körts för respektive meddelandeartikel. Sidan visar också de ytterligare fält som definierats för meddelandeposterna, samt värdena för dessa ytterligare fält.

I följande tabell hittar du beskrivningar av fälten på fliken **Meddelandeartiklar**.

<table>
<thead>
<tr>
<th>Fält</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr>
<td>Bearbetning</td>
<td>Namnet på den bearbetning som användes för att skapa meddelandeartikeln.</td>
</tr>
<tr>
<td>Meddelandeartikel</td>
<td>ID för meddelandeartikeln. Detta ID tilldelas automatiskt baserat på den nummerserie för <b>Meddelandeartikel</b> som definierats på sidan <b>Redovisningsparametrar</b>.</td>
</tr>
<tr>
<td>Datum för meddelandeartikel</td>
<td>Datumet då meddelandeartikeln skapades.</td>
</tr>
<tr>
<td>Meddelandets artikeltyp</td>
<td>Typen av meddelandeartikel. Flera typer av meddelandeartiklar kan ställas in för samma behandling (t.ex. <b>inkommande fakturor</b> och <b>utgående fakturor</b>). Detta fält kan endast fyllas i automatiskt när en faktura har lagts till artikeltabellen för meddelanden.</td>
</tr>
<tr>
<td>Status för meddelandeartikel</td>
<td><p>Faktisk status för e-postmeddelandet. Tillgängliga status beror på vilken typ av meddelandeobjekt som visas. Nedan följer några exempel:</p>
<ul>
<li><b>Ifyllt</b> – en post har lagts till i artikelregistret för meddelanden.</li>
<li><b>Utvärderad</b> – ytterligare attribut beräknades för meddelandeartikeln.</li>
<li><b>Rapporterad</b> – meddelandeartikeln har lagts till i en rapport.</li>
<li><b>Undantagen</b> – Denna status är användbar om vissa meddelandeobjekt ska undantas från en rapport innan denna exporteras.</li>
</ul>
</td>
</tr>
<tr>
<td>Överföringsdatum</td>
<td>För bearbetning som automatiskt överför en genererad rapport utanför systemet, datum då meddelandeartikeln överfördes.</td>
</tr>
<tr>
<td>Dokumentnummer</td>
<td>Detta fält fylls i automatiskt baserat på konfigurationen för åtgärden för ifyllnad av poster. Detta fält kan endast fyllas i automatiskt när en faktura har lagts till artikeltabellen för meddelanden.</td>
</tr>
<tr>
<td>Kontonummer</td>
<td>Kontonumret för kunden, leverantören eller något annat fältvärde, beroende på vilket fält som definierats i åtgärden för ifyllnad av poster. Detta fält kan endast fyllas i automatiskt när en faktura har lagts till artikeltabellen för meddelanden.</td>
</tr>
<tr>
<td>Meddelande</td>
<td>Numret på meddelandet. Detta nummer tilldelas automatiskt baserat på nummerserien för <b>Meddelande</b> som definieras på sidan <b>Redovisningsparametrar</b>.</td>
</tr>
<tr>
<td>Meddelandestatus</td>
<td>Faktisk status för elektroniskt meddelande.</td>
</tr>
<tr>
<td>Nästa åtgärd</td>
<td>Nästa åtgärd som kan startas för aktuell status för objektet visas.</td>
</tr>
</tbody>
</table>

Fliken **ytterligare fält** visar ytterligare fält för den markerade meddelandeartikeln och deras värden.

### <a name="run-processing"></a>Kör bearbetning

I åtgärdsfönstret väljer du **Kör bearbetning** om du vill köra bearbetningen för meddelandeartiklar. Att köra en viss åtgärd i dialogrutan **Kör bearbetning**, ange alternativet **Välj åtgärd** till **Ja** och välj en åtgärd. Om du vill köra hela bearbetningen lämna alternativet **Välj åtgärd** till **Nej**.

### <a name="generate-report"></a>Generera rapport

I åtgärdsfönstret väljer du **Generera rapport**. Den här knappen är kopplad till åtgärder av typen **Export av elektronisk rapportering**.

### <a name="update-status"></a>Uppdatera status

I åtgärdsfönstret väljer du **Uppdatera status** om du vill uppdatera statusen för en eller flera meddelandeartiklar. I dialogrutan **uppdatera status** använd snabbfliken **poster som ska ingå** för att välja meddelandeobjekt för uppdatering. Se till att du definierar urvalskriterierna korrekt, detta eftersom statusen för meddelandeartiklar uppdateras enligt dessa kriterier, den ursprungliga statusen för den valda åtgärden samt det värde som du anger i fältet **Ny status**. När en statusuppdatering har slutförts kan det vara svårt att avgöra vilka artiklar som precis har uppdaterats. Därför är det svårt att återställa statusuppdateringen.

### <a name="electronic-messages"></a>Elektroniska meddelanden

I åtgärdsfönstret väljer du **Elektroniska meddelanden** om du vill granska ett elektroniskt meddelande som är relaterat till vald meddelandeartikel.

Du kan också granska de filer som är relaterade till en viss meddelandeartikel. Välj fältet **Meddelande** för meddelandeartikeln eller välj **Elektroniska meddelanden** i åtgärdsfönstret. På sidan **Elektroniskt meddelande** markerar du meddelandet som du vill granska filer för och väljer sedan knappen **Bilaga** (gemsymbolen) i det övre högra hörnet på sidan.

Sidan **Bilagor** visar de bilagor som hör till meddelandet. Om du vill visa en fil markerar du den i listan till vänster och markerar **öppna** i åtgärdsfönstret.

### <a name="original-document"></a>Ursprungsdokument

Välj **Ursprungsdokument** i åtgärdsfönstret för att öppna det ursprungliga dokumentet för den markerade meddelandeartikeln.
