---
title: "Installera komponenter för ett jobb"
description: "Det här ämnet beskriver begreppsmässig element att ett projekt kan innehålla och ger exempel på hur du kan använda dessa objekt i din organisation."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: d96b1f01a5cb4370436888deae8fd4835a0dbb80
ms.openlocfilehash: b8143db5b133337603a7f2f46028d91bb81cd947
ms.lasthandoff: 03/31/2017


---

# <a name="setting-up-the-components-of-a-job"></a>Installera komponenter för ett jobb

Det här ämnet beskriver begreppsmässig element att ett projekt kan innehålla och ger exempel på hur du kan använda dessa objekt i din organisation. 

Innan du kan skapa jobb måste du ställa in vissa Referensinformation. Du kan skapa ett jobb som har bara ett namn. Men genom att lägga till ytterligare information, till exempel titel, anger du standardvärden för befattningar som tilldelats till projektet. Dessutom kan del av informationen som du anger användas för att filtrera kompensationsplaner på specifika jobb. Om du vill ställa in kvalifikationer som du kan använda för att filtrera kompensationsplaner på specifika jobbet bör du ställa in jobbfunktioner och jobbtyper innan du registrerar jobb. Genom att dessa standardvärden som finns tillgängliga, sparar du tid när du lägger till befattningar för jobbet. 

Vissa jobbinformation som befattning, typ och funktionen är datumet gäller. Om du sedan tittar på jobbet för ett skapandedatum och skapar ett jobb redan idag, men Lägg inte till den här informationen till senare, visas inte den här informationen. Därför bör du skapa vissa av de här innan du tar emot den. På så sätt ange information till nya jobb när de skapas.

## <a name="job-titles"></a>Jobbtitlar
Innan du skapar jobb måste du ställa in titlar för jobben. Befattningar ärver jobbtitlar från jobben som befattningarna är kopplade till. 

Underhåll jobbtitlar med hjälp av den **titlar** som du kan öppna genom att använda sökfunktionen. På den ** titlar ** sidan, ange rubriker som du vill använda för ditt projekt.

## <a name="job-types"></a>Jobbtyper
Du kan använda jobbtyper för att gruppera liknande jobb i kategorier. Jobbtyper som inte behövs. Om du tänker använda jobbtyper när du ställer in berättiganderegler för kompensationshantering bör du ställa in jobbtyper innan du ställer in jobb. Är några exempel på jobbtyper heltid och deltid eller betala lön och varje timme. Du kan underhålla jobbtyper med hjälp av den **jobbtyper** sida. I den **jobbtyper** kan du ange ett namn och en kort beskrivning av jobbtypen. I den **status undanta** väljer du ett av följande alternativ för att ange verkligt arbete Standards Act FLSA () befrielsestatus för jobb som har den här jobbtypen:

-   **Undanta** – jobb är undantagna från övertid under FLSA.
-   **Ej befriat** – jobb som inte är undantagna från övertid under FLSA.
-   **Gäller inte** – artikeldisponering FLSA inte gäller.

## <a name="job-functions"></a>Jobbfunktioner
Jobbet vägkorsningar beskriver funktionella kategorier på hög nivå och relaterade uppgifter på hög nivå. Funktioner som inte behövs. Du kan använda jobbfunktioner med andra jobbtyper, för att filtrera kompensationsplaner på specifika jobb. Du kopplar jobbfunktioner och jobbtyper till kompensationsplaner genom att ställa in berättiganderegler i formuläret **berättiganderegler** sida. Du kan sedan koppla en uppsättning nivåer till en kompensationsplan som gäller för specifika kombination av jobbtyp och jobbfunktion som du definierat med en berättiganderegel. (Dessa funktioner gäller både fasta kompensationsplaner och variabla kompensationsplaner.) Men om du planerar att använda när du ställer in berättiganderegler för kompensationshantering jobbfunktioner bör du ställa in jobbfunktioner innan du registrerar jobb. Nedan visas några exempel på jobbfunktioner.

| Jobb           | Jobbfunktion      |
|---------------|-------------------|
| Försäljningschef | Mellannivå Manager |
| Redovisare    | Ansvariga     |

Du kan underhålla jobbfunktioner med hjälp av den **jobbfunktioner** sida. I den **jobbfunktioner** kan du ange ID-kod och en kort beskrivning av jobbfunktionen.

## <a name="job-tasks"></a>Jobbuppgifter
Projektaktiviteter beskriver de grundläggande aktiviteter som ska utföra en arbetare som står i ett läge för ett projekt. Samma projektaktiviteten kan läggas till flera jobb och befattningar för de jobb som använder de projektaktiviteterna. Nedan visas några exempel på projektaktiviteter.

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
<li><strong>Perf granskning</strong> – granska jobbet säljarnas resultat.</li>
<li><strong>ABS granskning</strong> – Godkänn eller Avvisa ledighetsansökningar eller registreringar för varje säljare.</li>
</ul></td>
</tr>
<tr class="even">
<td>Redovisare</td>
<td><strong>FIN-rapport</strong> – förelägga ekonomichef veckovis ekonomirapporter.</td>
</tr>
</tbody>
</table>

Du kan underhålla projektaktiviteter med hjälp av den **projektaktiviteter** sida. I den **projektaktiviteter** kan du ange ett namn och en beskrivning av projektaktiviteten. I den **notering** fält du kan ange ytterligare information. Anteckningarna kan uppdateras för ett specifikt projekt utan att ändra de anteckningar som du har angett.

## <a name="areas-of-responsibility"></a>Ansvarsområden
Du kan använda ansvarsområden för att ange arbetsroller, processer och produkter som personen står i ett läge för ett projekt som är ansvarig för. För ett projekt som heter "Revisorn" kan ett ansvarsområde exempelvis "Ekonomisk rapportering för produkten A." Du Underhåll ansvarsområden med hjälp av den **ansvarsområden** som du hittar genom att använda sökfunktionen. I den **ansvarsområden** kan du ange ett namn och en beskrivning för ansvarsområdet. I den **notering** fält du kan ange ytterligare information. Anteckningarna kan uppdateras för ett specifikt projekt utan att ändra de anteckningar som du har angett.


