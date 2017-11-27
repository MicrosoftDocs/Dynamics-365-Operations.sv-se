---
title: "Installera komponenter för ett jobb"
description: "Det här avsnittet beskriver begreppsmässiga element som ett projekt kan innehålla och ger exempel på hur du kan använda dessa objekt inom din organisation."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle
audience: Application User
ms.author: rschloma
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Retail
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 962b3084c5340813d1697cab680621350510d4b9
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="setting-up-the-components-of-a-job"></a>Installera komponenter för ett jobb

[!include[banner](includes/banner.md)]

[!include[retail name](includes/retail-name.md)]


Det här avsnittet beskriver begreppsmässiga element som ett projekt kan innehålla och ger exempel på hur du kan använda dessa objekt inom din organisation. 

Innan du kan skapa nya jobb måste du skapa viss referensinformation. Du kan skapa ett jobb som har bara ett namn. Genom att lägga till ytterligare information, till exempel titel, anger du emellertid standardvärden för de befattningar som tilldelats till jobbet. Dessutom kan en del av informationen som du anger användas för att filtrera kompensationsplaner på specifika jobb. Om du vill konfigurera berättiganden som du kan använda för att filtrera kompensationsplaner på ett specifikt jobb, bör du ställa in jobbfunktioner och jobbtyper innan du registrerar jobb. Genom att ha dessa standardvärden tillgängliga sparar du tid när du lägger till befattningar för jobbet. 

Viss jobbinformation, exempelvis befattning, typ och funktion, har giltighetsdatum. Om du skapar ett jobb redan idag men inte lägger till denna information förrän senare och sedan tittar på jobbet från och med skapandedatum, så visas inte denna information. Därför bör du skapa en del av denna referensinformation innan du behöver den. På så sätt kan du lägga till informationen till nya jobb när dessa skapas.

## <a name="job-titles"></a>jobbtitlar
Innan du skapar jobb måste du ställa in titlar för jobben. Befattningar ärver jobbtitlar från jobben som befattningarna är kopplade till. 

Underhåll jobbtitlar med hjälp av sidan **Titlar**, som du kan öppna genom att använda sökfunktionen. På sidan **Titlar ** anger du de rubriker som du vill använda för dina jobb.

## <a name="job-types"></a>Jobbtyper
Du använder jobbtyper för att gruppera liknande jobb i kategorier. Jobbtyper krävs inte. Om du tänker använda jobbtyper när du ställer in berättiganderegler för kompensationshantering bör du ställa in jobbtyper innan du ställer in jobb. Några exempel på jobbtyper är heltid och deltid, eller lön och timpenning. Du kan underhålla jobbtyper med hjälp av sidan **Jobbtyper**. På sidan **Jobbtyper** anger du ett namn och en kort beskrivning för jobbtypen. I fältet **Befrielsestatus** väljer du ett av följande alternativ för att ange befrielsestatusen Fair Labor Standards Act (FLSA) befrielsestatus för jobb som har den här jobbtypen:

-   **Undantag** – Jobb är befriade från övertid under FLSA.
-   **Icke-undantag** – Jobb är inte befriade från övertid under FLSA.
-   **Gäller inte** – FLSA-täckning gäller inte.

## <a name="job-functions"></a>Jobbfunktioner
Jobbkopplingar beskriver funktionella kategorier på hög nivå och relaterar uppgifter på hög nivå. Jobbfunktioner krävs inte. Du kan använda jobbfunktioner tillsammans med jobbtyper för att filtrera kompensationsplaner till specifika jobb. Du kopplar jobbfunktioner och jobbtyper till kompensationsplaner genom att ställa in berättiganderegler på sidan **Berättiganderegler**. Du kan sedan lägga till en nivåserie till en kompensationsplan som gäller den specifika kombinationen av en jobbtyp och en jobbfunktion som du har definierat med en berättiganderegel. (Dessa funktioner gäller både planer för fast kompensation och planer för variabel kompensation.) Om du emellertid tänker använda jobbfunktioner när du skapar berättiganderegler för kompensationshantering, bör du skapa jobbfunktioner innan du skapar jobb. Följande tabell anger några exempel på jobbfunktioner.

| Jobb           | Jobbfunktion         |
|---------------|----------------------|
| Försäljningschef | Chef på mellannivå    |
| Redovisare    | Yrkespersoner        |

Du underhåller jobbtyper med hjälp av sidan **Jobbfunktioner**. På sidan **Jobbfunktioner** anger du en identifieringskod och en kort beskrivning för jobbfunktionen.

## <a name="job-tasks"></a>Jobbuppgifter
Jobbuppgifter beskriver de grundläggande uppgifter som en anställd i en befattning måste utföra. Samma jobbuppgift kan läggas till i flera jobb och i befattningar för de jobb som använder dessa jobbuppgifter. Följande tabell anger några exempel på jobbuppgifter.

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
<li><strong>Resultatgranskning</strong> – Granska varje säljares jobbprestation.</li>
<li><strong>Frånvarogranskning</strong> – Godkänn eller avvisa varje säljares frånvaroförfrågningar eller -registreringar.</li>
</ul></td>
</tr>
<tr class="even">
<td>Redovisare</td>
<td><strong>FIN-rapport</strong> – Visa aktuella veckovisa ekonomiska rapporter för ekonomichefen.</td>
</tr>
</tbody>
</table>

Du kan underhålla jobbuppgifter med hjälp av sidan **Jobbuppgifter**. På sidan **Jobbtyper** anger du ett namn och en kort beskrivning för jobbuppgiften. Om du vill kan du ange ytterligare information i fältet **Anteckningar**. Anteckningarna kan uppdateras för ett specifikt projekt utan att ändra de anteckningar som du har angett.

## <a name="areas-of-responsibility"></a>Ansvarsområden
Använd ansvarsområden för att indikera arbetsroller, processer och produkter som en arbetare i en befattning bär ansvar för. Till exempel: För ett jobb vid namn "Revisor" kan ett ansvarsområde vara "Ekonomisk rapporteringen för produkt A”. Du underhåller ansvarsområden med hjälp av sidan **Ansvarsområden**, som du hittar genom att använda sökfunktionen. På sidan **Ansvarsområden** anger du ett namn och en beskrivning för ansvarsområdet. Om du vill kan du ange ytterligare information i fältet **Anteckningar**. Anteckningarna kan uppdateras för ett specifikt projekt utan att ändra de anteckningar som du har angett.




