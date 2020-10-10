---
title: Rullande inventering
description: Den här artikeln beskriver hur du kan använda rullande inventering tillsammans med den lagerställelösning som är tillgänglig i Lagerstyrning. Den här artikeln gäller inte för den lagerställelösning som är tillgänglig i Lagerhantering.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage, SalesShipmentDeviation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 50671
ms.assetid: 49f5c431-b043-4170-aa24-b7d5d1ee063e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8352df2de5daf994895eb7ef40866490a7619652
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830510"
---
# <a name="cycle-counting"></a>Rullande inventering

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver hur du kan använda rullande inventering tillsammans med den lagerställelösning som är tillgänglig i Lagerstyrning. Den här artikeln gäller inte för den lagerställelösning som är tillgänglig i Lagerhantering.

Rullande inventering är en lagerställesprocess som du kan använda för att kontrollera lagerbehållningsartiklar. Processen för rullande inventering kan beskrivas i tre steg:

1.  **Skapa arbetsuppgift för rullande inventering** – arbetsuppgift för rullande inventering kan skapas automatiskt baserat på tröskelparametrar för artiklar eller genom att använda en plan för rullande inventering. Du kan också skapa rullande inventering manuellt, med hjälp av artikeln eller lagerställeparametrar på sidan **Rullande inventeringsarbete efter artikel** efter på sidan **Rullande inventeringsarbete efter plats**.
2.  **Bearbeta rullande inventering** – Efter att du har skapat det rullande inventeringsarbetet utför du det rullande inventeringsarbetet genom att räkna artiklar på en lagerplats och sedan ange resultatet i Dynamics 365 Supply Chain Management med hjälp av en mobil enhet. Alternativt kan du inventera artiklar i ett lagerställe utan att skapa rullande inventeringsarbete. Den här processen kallas för *rullande inventering av typen spot*.
3.  **Lösa avvikelser i det räknade värdet** – Efter en rullande inventering har alla artiklar som har avvikelser i det inventerade värdet en arbetsstatus som är **Pågående granskning** på sidan **Allt arbete**. Du kan lösa dessa skillnader på sidan **Granskning av väntande rullande inventeringsarbete**.

I bilden nedan visas processen för rullande inventering. ![Bearbeta flöde rullande inventering](./media/performcyclecountinginawarehouselocation.jpg)

## <a name="cycle-counting-prerequisites"></a>Förutsättningar för rullande inventering
Följande tabell visar förutsättningarna som krävs och måste finnas på plats innan du kan använda rullande inventering.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Förutsättning</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Artikel</td>
<td>Artikeln måste aktiveras för lagerhanteringsprocesser.</td>
</tr>
<tr class="even">
<td>Lagerställe</td>
<td>Lagerstället måste aktiveras för lagerhanteringsprocesser. Om du vill aktivera lagerstället för lagerhanteringsprocesser, väljer du lagerstället på sidan <strong>Lagerställen</strong> och markerar sedan alternativet <strong>Använd lagerstyrningsprocesser</strong>. Om du vill att arbetare ska kunna flytta lastpallar under en rullande inventering markerar du alternativet <strong>Tillåt att lastpallar flyttas under rullande inventering</strong> på snabbfliken <strong>Lagerstyrning</strong>.</td>
</tr>
<tr class="odd">
<td>Arbetspooler</td>
<td>Alternativ: Skapa en arbetspool för att skilja lagerställearbetet baserat på typ av arbete (i det här fallet arbete med rullande inventering).</td>
</tr>
<tr class="even">
<td>Platser</td>
<td>Aktivera rullande inventering för platser. Du aktiverar rullande inventering för ett lagerställe genom att markera alternativet <strong>Tillåt rullande inventering</strong> på sidan <strong>Platsprofiler</strong>.</td>
</tr>
<tr class="odd">
<td>Parametrar för lagerstyrning</td>
<td>Ställ in parametrar för rullande inventering. På sidan <strong>Parametrar för lagerstyrning</strong>, ange standardjusteringstyp, arbetsklass-ID och arbetsprioritet för rullande inventering.</td>
</tr>
<tr class="even">
<td>Mobil enhet</td>
<td><ul>
<li>Skapa ett menyalternativ för någon av följande metoder på sidan <strong>Menyalternativ på mobil enhet</strong>:
<ul>
<li>Användarstyrd rullande inventering</li>
<li>Systemstyrd rullande inventering</li>
<li>Rullande inventeringsgruppering</li>
<li>Rullande inventering av typen Spot</li>
</ul>
</li>
<li>Ställa in en meny för den mobila enheten.</li>
<li>Skapa ett arbetsuppgiftsanvändarkonto och tilldela en mobilenhetsmeny till arbetsuppgiftsanvändar-ID:t.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Relaterad inställningsuppgift</td>
<td>Ställa in en plan för rullande inventering för en lagerplats.</td>
</tr>
</tbody>
</table>

## <a name="automatically-create-cycle-counting-work"></a>Skapa rullande inventeringsarbete automatiskt
Det finns två sätt att schemalägga återkommande skapande av arbete för rullande inventering: ställa in trösklar för rullande inventering eller ställa in planer för rullande inventering.

-   En tröskel för rullande inventering anger kvantitets- eller procentgränsen för lagerartiklar. En arbetsuppgift för rullande inventering skapas automatiskt när tröskelgränsen nås.
-   En plan för rullande inventering skapar rullande inventeringsarbete antingen direkt eller periodiskt via ett batchjobb. När rullande inventeringsarbete skapas innehåller raden för rullande inventering information om vilken plats som ska räknas. Lagerbehållningen som är associerad med den här platsen är inte spärrad och är därför tillgänglig för reservation och utgående bearbetning, även om öppet inventeringsarbete finns.

### <a name="create-cycle-counting-work-based-on-threshold-parameters-for-items"></a>Skapa arbetsuppgift för rullande inventering baserat på tröskelparametrar för artiklar

En arbetsuppgift för rullande inventering kan skapas när antalet artiklar är under ett specifikt tröskelvärde för en plats. Det finns till exempel 60 artiklar på en plats som har en tröskel för rullande inventering på 40. Under en försäljningsordertransaktion plockas 25 artiklar från platsen och placeras på en mellanlagringsplats. Eftersom det nya artikelantalet är 35, d.v.s. mindre än tröskelkvantiteten, skapas arbete för rullande inventering automatiskt för platsen.

### <a name="schedule-cycle-counting-work"></a>Tidsplanera arbete för rullande inventering

Du kan schemalägga planer för rullande inventering för att skapa rullande inventeringsarbete direkt eller periodiskt. Om du ställer in planer för rullande inventering kan du styra arbetspoolen som arbetet för rullande inventering skapas för, det maximala antalet rullande inventeringar som skapas för artiklar på andra platser, och antal dagar före en lagerställeplats inventeras igen. Exempel: en artikel är tillgänglig på tre platser på lagerstället och det maximala antalet rullande inventeringar har ställts in på **2**. I det här fallet, när du kör planen för rullande inventering kommer två rullande inventeringar att skapas för de två platser där artikeln finns. Som ett annat exempel, du ställer in antal dagar mellan rullande inventeringar till **5**. I detta fall skapas arbete för rullande inventering varje fem dagar. Men om arbete för rullande inventering bearbetas på dag tre kommer nästa arbete för rullande inventering skapas fem dagar efter att den sista rullande inventeringen bearbetades på dag åtta.

## <a name="create-cycle-counting-work-manually"></a>Skapa arbetsuppgift för rullande inventering manuellt
Om du vill skapa arbete för rullande inventering manuellt, kan du använda sidan **Rullande inventeringsarbete efter artikel** eller **Rullande inventeringsarbete efter plats**. Du kan ange det högsta antalet rullande inventeringar att skapa. Om till exempel lagerchefen anger ett värde på **5** skapas ett arbete för rullande inventering för fem platser även om artikeln finns på 10 olika platser. Du kan även välja ett ID för arbetspool att tilldela de skapade ID:na för arbetet med rullande inventering. När ett arbetspool-ID bearbetas för rullande inventering, bearbetas de ID:n som är tilldelade till arbetspoolen som en grupp.

## <a name="perform-a-cycle-count-by-using-a-mobile-device"></a>Utför en rullande inventering med hjälp av en mobil enhet
Det finns flera sätt att genomföra arbetet med rullande inventering genom att använda Supply Chain Management på en mobil enhet:

-   **Användarstyrd** – arbetaren kan ange ett arbets-ID för rullande inventering som har statusen **Öppen**.
-   **Systemstyrd** – Supply Chain Management tilldelar ett arbets-ID för rullande inventering.
-   **Gruppering av rullande inventering** – arbetstagare kan gruppera ID:n för pågående rullande inventeringar som är specifika för en viss plats, zon eller arbetspool.
-   **Rullande inventering av typen Spot** – Arbetaren kan genom att ange en lagerplats räkna artiklar på ett lagerställe när som helst utan att skapa en arbetsuppgift för rullande inventering. Om arbetaren vill utföra rullande inventering av typen spot för en plats, anger hen plats-ID.

Följande procedur visar hur du kan utföra rullande inventering av typen spot genom att använda en mobil enhet. Instruktionerna som arbetaren ser på enheten varierar beroende på inställningarna för menykommando för inventering av typen spot.

1.  Välj menykommandot på den mobila enheten för att bearbeta Rullande inventering av typen Spot.
2.  Registrera platsen för att utföra inventering av typen spot för.
3.  Registrera och bekräfta artikelnumret och den inventerade artikelkvantiteten. **Obs!** Statusen för rullande inventeringsarbete uppdateras till antingen **Pågående granskning** eller **Stängd** på sidan **Allt arbete** beroende på de parametrar som anges på sidan **Arbetare**.
4.  Valfritt: Upprepa steg 3 för de artiklar som återstår på platsen och bekräfta att det inte finns några ytterligare artiklar som är tillgängliga för inventering.

## <a name="resolve-cycle-counting-differences"></a>Lösa avvikelser för rullande inventering
En avvikelse för rullande inventering inträffar i följande scenarier om alternativet **Är ansvarig för rullande inventering** är inställd till **Nej** för ett arbetaranvändar-ID:

-   Värdet från den rullande inventeringen är inte inom de avvikelsegränser som anges i fälten **Gräns för högsta procentandel** eller **Gräns för högsta kvantitet** på sidan **Arbetsanvändare**. Till exempel är tillgänglig lagerkvantitet på en plats 50, och avvikelsegränsen för arbetsanvändaren är 10. Om arbetsanvändaren anger ett värde som inte är mellan 40 och 60, uppstår en skillnad.
-   Värdet från den rullande inventeringen skiljer sig från lagerbehållningskvantiteten och det finns inga angivna avvikelsegränser.

Du kan justera avvikelser i det beräknade värdet och sedan acceptera det beräknade värdet på sidan **Granskning av väntande rullande inventering**. Du kan verifiera det modifierade antalet för artikelkvantiteten på sidan **Behållning efter plats**. Värdet från den rullande inventeringen åsidosätts om skillnaden inte kan godkännas.

## <a name="additional-resources"></a>Ytterligare resurser
[Ställ in mobila enheter för lagerarbete](configure-mobile-devices-warehouse.md)



