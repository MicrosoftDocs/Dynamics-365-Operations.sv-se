---
title: Rapportdefinitioner i designer för ekonomiska rapporter
description: Den här artikeln innehåller information om rapportdefinitioner.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7d5531112cfb803912849af3af785b2a69a79f3d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093424"
---
# <a name="report-definitions-in-financial-report-designer"></a>Rapportdefinitioner i designer för ekonomiska rapporter

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller information om rapportdefinitioner. En rapportdefinition är en rapportkomponent (eller byggblock) som använder en raddefinition, en kolumndefinition och valfri rapportträddefinition för att skapa en rapport. En rapportdefinition innehåller också alternativ och inställningar för att anpassa en rapport. 

En rapportdefinition är en rapportkomponent (eller byggblock) som använder en raddefinition, en kolumndefinition och valfri rapportträddefinition för att skapa en rapport. En rapportdefinition innehåller också alternativ och inställningar som du kan använda för att anpassa en rapport. När du har definierat raddefinitioner och kolumndefinitioner, måste du kombinera dem i en rapportdefinition. I det här läget definierar du också andra aspekter av definitioner, till exempel detaljnivå och rapportdatum. Du kan sedan spara och skapa en rapport. Ekonomist rapportering omfattar följande detaljnivåer:

- Ekonomi
- Ekonomisk och Konto
- Ekonomisk, Konto och Transaktion

Däremot är det inte säkert att transaktionsinformation finns tillgänglig i rapporter, beroende på hur informationen är lagrad i Microsoft Dynamics ERP-systemet.

## <a name="create-a-report-definition"></a>Skapa en rapportdefinition
1. I Report Designer i menyn **Fil** klickar du på **Nytt** och väljer sedan **Rapportdefinition**.
2. Ange lämplig information i flikarna **Rapport** som krävs på **Utleverans och fördelning**, **Sidhuvud och sidfot** och **Inställningar**.

## <a name="contents-of-a-report-definition"></a>Innehåll i en rapportdefinition
I följande register finns beskrivningar av flikarna i en rapportdefinition och hur informationen används.

<table>
<thead>
<tr>
<th>Tabb</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr>
<td>Rapport</td>
<td>Skapa en rapport, konfigurera en rapport eller ändra en befintlig rapport.</td>
</tr>
<tr>
<td>Utleverans och fördelning</td>
<td>Ändra rapportens utleveranstyp och mål.</td>
</tr>
<tr>
<td>Huvud och sidfot</td>
<td>Definiera och formatera rapportens sidhuvud och sidfot. Du kan till exempel lägga till text eller bilder till sidhuvudet eller sidfoten. Ekonomisk rapportering stöder .bmp-, .jpg- och .png-filer för bilder. Du kan också lägga till autotextkoder om du vill infoga annan information som till exempel företagsnamn, rapportnamn eller sidnummer.</td>
</tr>
<tr>
<td>Inställningar</td>
<td>Ange rapportdefinitioninställningar, till exempel följande inställningar:
<ul>
<li>Formatering och avrundningsbelopp</li>
<li>Formatdetaljrapporter</li>
<li>Formatrapporteringsträd</li>
<li>Skapa rapport över inleveransavvikelser</li>
<li>Ange valutakonvertering</li>
<li>Delsumma- och filterkontodetaljer</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Ytterligare resurser

[Ekonomisk rapportering](financial-reporting-intro.md)
