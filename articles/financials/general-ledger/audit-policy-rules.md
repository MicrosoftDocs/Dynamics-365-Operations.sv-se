---
title: "Regler för granskningspolicy"
description: "Du kan använda granskningsprinciper för att utvärdera utgiftsrapporter, leverantörsfakturor och inköpsorder för att säkerställa att de överensstämmer med policyregler som du skapar. Alla regler som är associerade med en granskningspolicy körs i batchläge enligt en tidsplan som du anger.  Varje policyregel är en instans av en policyregeltyp. Endast en policyregel i taget kan gälla för en policyregeltyp."
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 04217e162090720d2a48c96aa9356cea2dbfa230
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="audit-policy-rules"></a>Regler för granskningspolicy

[!INCLUDE [banner](../includes/banner.md)]

Du kan använda granskningsprinciper för att utvärdera utgiftsrapporter, leverantörsfakturor och inköpsorder för att säkerställa att de överensstämmer med policyregler som du skapar. Alla regler som är associerade med en granskningspolicy körs i batchläge enligt en tidsplan som du anger.  Varje policyregel är en instans av en policyregeltyp. Endast en policyregel i taget kan gälla för en policyregeltyp. 

<a name="queries-and-query-types"></a>Frågor och frågetyper
-----------------------

När du skapar en granskningspolicyregel, väljer du först en policyregeltyp. Policyregeltypen anger vilken programobjektträdfråga som ska användas som utgångspunkt för att skapa policyregeln. Den kan också ange den frågetyp som ska användas för policyregeln. Frågan bestämmer vilket källdokument som policyregeln utvärderar. Den visar även fälten i källdokumentet som identifierar både den juridiska personen och det datum som ska användas när dokument har valts för granskning. Frågetypen styr standardfälten på frågesidan och sidan för granskningspolicyregler. Följande tabell visar de frågetyper som finns tillgängliga för granskningspolicyregler.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Frågetyp</th>
<th>Syfte</th>
<th>Mer information</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Villkor</td>
<td>Utvärdera källdokumentattribut mot angivna värden.</td>
<td></td>
</tr>
<tr class="even">
<td>Sammansättning</td>
<td>Utvärdera flera källdokument eller källdokumentrader mot en policyregel genom summering av numeriska värden.</td>
<td></td>
</tr>
<tr class="odd">
<td>Sampling</td>
<td>Välj slumpmässigt en viss procent av källdokumenten som ska utvärderas för policykränkningar.</td>
<td>När du väljer det här alternativet använder du sidan för regler för granskningspolicy för att ange procenten av dokument som ska väljas slumpmässigt för granskning.</td>
</tr>
<tr class="even">
<td>Duplicera</td>
<td>Utvärdera källdokument för att bestämma om de innehåller dubblettposter i angivna fält.</td>
<td>När du väljer det här alternativet använder du sidan för granskningspolicyregler för att ange antal dagar du vill lägga till början av dokumentvalsdatumintervallet när dokument utvärderas om det finns dubblettposter.</td>
</tr>
<tr class="odd">
<td>Listsökning</td>
<td>Utvärdera källdokument för specifika enheter.</td>
<td>Rotdokumentet för frågan definierar dokumentet som revideras. Frågan måste vara en listfråga som innehåller en referens till det registret dirpartytable. Detta alternativ kan användas endast med följande AOT-frågor:
<ul>
<li><span class="ui">AuditPolicyExpenseList</span> (Utgiftsrapport som övervakas av medarbetare)</li>
<li><span class="ui">AuditPolicyPurchList</span> (Inköpsorder som övervakas av leverantörer)</li>
<li><span class="ui">AuditPolicyVendInvoiceList</span> (Leverantörsfaktura som övervakas av leverantörer)</li>
</ul>
Ange övervakade enheter på sidan för regler för granskningspolicyn när du väljer det här alternativet.</td>
</tr>
<tr class="even">
<td>Nyckelordssökning</td>
<td>Utvärdera källdokument för att bestämma om de innehåller vissa word.</td>
<td>Ange de ord som ska sökas på sidan för regler för granskningspolicyn när du väljer det här alternativet. Sidan för regler för granskningspolicyn innehåller även alternativ som låter dig ange de register och fält som ska utvärderas för de ord som du har angett.</td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a>Gemensamma parametrar
Alla policyregler för en viss granskningspolicy delar samma batchparametrar och samma datumintervallet för dokumenturval. Parametrarna för policyn anges på sidan Ytterligare alternativ.



<a name="see-also"></a>Se även
--------

[Överträdelser av granskningspolicyn och ärenden](audit-policy-violations-cases.md)
[Definiera granskningspolicyer för källdokument](tasks/define-audit-policies-source-documents.md)



