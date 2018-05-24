---
title: Servicehantering
description: "Använd Servicehantering för att fastställa serviceavtal och serviceabonnemang, hantera serviceordrar och kundförfrågningar, och för att hantera och analysera leverans av tjänster till kunder."
author: YuyuScheller
manager: AnnBe
ms.date: 05/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 02cdf4615e2071f2b7de2e86b6f9e6637c6e5d8d
ms.openlocfilehash: 236ab21b2d1c5a4e82270e5381d163e97437cb7f
ms.contentlocale: sv-se
ms.lasthandoff: 05/09/2018

---


# <a name="service-management"></a>Servicehantering 

[!include [banner](../includes/banner.md)]


Använd **Servicehantering** för att fastställa serviceavtal och serviceabonnemang, hantera serviceordrar och kundförfrågningar, och för att hantera och analysera leverans av tjänster till kunder. Du kan använda serviceavtal när du vill definiera resurser som används vid ett vanligt servicebesök. Du kan också använda serviceavtal du vill visa hur resurserna kan faktureras kunden. Ett serviceavtal kan även innehålla ett serviceavtal som anger svarstider, och erbjuder verktyg för att registrera den faktiska tiden.

Du kan skapa serviceorder du vill hantera information om schemalagda och icke tidsplanerade servicebesök av en servicetekniker till en kunds anläggning. Serviceorder innehåller information som:

1.  Arbetstiderna som serviceteknikern ska utföra

2.  Typ av tjänst eller reparation

3.  Artikeln som ska repareras, inklusive information om symptom och diagnoser

4.  Utgifter och avgifter som är relaterade till tjänsten eller reparationen

Kunder kan skicka in serviceförfrågningar via Internet med hjälp av Enterprise Portal. Du kan ta emot, behandla och skicka ut dessa frågor. När du har skapat en serviceorder kan du använda servicefaser för att övervaka förlopp och ange regler som styr vilka åtgärder som ska aktiveras i varje fas. När en serviceorder är avslutad, kan du godkänna ordern för att bekräfta att den är slutförd, och sedan bokföra ordern för att starta fakturaprocessen.

Använd rapporteringsverktygen för att övervaka serviceordermarginaler och abonnemangstransaktioner, och skriva ut arbetsbeskrivningar och arbetsinleveranser.

## <a name="business-processes"></a>Affärsprocesser

I följande diagram illustreras den höga nivån av affärsprocesser för **servicehantering**, och visar var serviceprocesser integreras med andra moduler i Microsoft Dynamics 365 for Finance and Operations.

[![Affärsprocessdiagram för servicehantering](./media/sm_home_page.gif)](./media/sm_home_page.gif)

## <a name="service-management-at-a-glance"></a>Snabb överblick över servicehantering

<table>
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Viktiga uppgifter</p></th>
<th><p>Primära formulär</p></th>
<th><p>Populära rapporter</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Uppfyll serviceavtal</a></p></td>
<td><p><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Serviceavtal (formulär)</a></p></td>
<td><p><strong>Serviceordermarginal</strong></p></td>
</tr>
<tr class="even">
<td><p>Hantera kundförfrågningar</a></p></td>
<td><p><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Serviceorder (formulär)</a></p></td>
<td><p><strong>Arbetsbeskrivning</strong></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Utförseltavla (formulär)</a></p></td>
<td><p><strong>Transaktion - abonnemang</strong></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p><strong>Abonnemangsavgiftstransaktioner</strong></p></td>
</tr>
</tbody>
</table>


## <a name="integration-of-service-management"></a>Integrering av servicehantering

Servicehanteringen kan integreras med följande moduler i Microsoft Dynamics 365 for Finance and Operations:

  - [Försäljning och marknadsföring](../sales-marketing/overview-sales-marketing.md)

  - [Personal](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/index)

  


