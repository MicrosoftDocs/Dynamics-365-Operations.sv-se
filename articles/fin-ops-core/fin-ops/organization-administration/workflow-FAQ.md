---
title: Vanliga frågor om arbetsflöde
description: Detta avsnitt besvarar några vanliga frågor om arbetsflödessystemet.
author: ChrisGarty
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 785b14d20a647ea2187f311f1cd056b8181d4849
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694066"
---
# <a name="workflow-faq"></a>Vanliga frågor om arbetsflöde

[!include [banner](../includes/banner.md)]

Detta avsnitt besvarar några vanliga frågor om arbetsflödessystemet.

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Varför tas flera meddelanden emot när en arbetsuppgift avvisas?
När en arbetsuppgift har avvisats kommer detta arbetsobjekt slutföras som avvisat. En annan arbetsuppgift skapas och tilldelas till upphovsmannen. Detta innebär att det finns ett meddelande till upphovsmannen för den avvisade arbetsuppgiften och ett separat meddelande till användaren som är tilldelad till den nya ”ändringsbegärda” arbetsuppgiften. 

Varje meddelande är för en olika arbetsuppgift, men likheten kan vara förvirrande. Vi undersöker sätt att förbättra detta i framtida versioner.

## <a name="why-are-my-workflow-exports-failing"></a>Varför fungerar inte min arbetsflödesexport?
Det finns en begränsning i funktionen för att exportera arbetsflöden som förhindrar att arbetsflödesnamn innehåller fler än 48 tecken. Om du använder ett namn som är längre än 48 tecken kan felmeddelandet "servern kunde inte autentisera begäran" visas och/eller förhindra att en fil exporteras utan filtyp. Följande blogginlägg innehåller mer information om [Felsökning av arbetsflödesexport](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a>Kan den som skickar ett arbetsflöde också godkänna arbetsflödet?
Ja, en avsändare av ett arbetsflöde kan också godkänna arbetsflödet om det är konfigurerat på det sättet. Du kan förhindra detta genom att ställa in **Systemadministration > Arbetsflöde > Arbetsflödesparametrar > Allmänt > Godkännaren > Tillåt inte godkännande av avsändare** till **Ja**.

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a>Kan jag lägga till notifieringar i arbetsflöden för att skicka meddelanden till användarna?
Här följer några viktiga områden som du kan använda för att lägga till notifieringar i arbetsflöden för meddelanden:
- Notifieringar jämfört med meddelandefunktioner för arbetsflöde
    - Notifieringar kan ställas in för poständringar. Arbetsflöden ändrar poster så det går att ställa in en notifiering som hör till en poständring som orsakas av ett arbetsflöde. Eftersom arbetsflöden har olika inbyggda meddelandealternativ, är det dock inte idealiskt att använda notifieringar.
- Standardmeddelanden från arbetsflöden 
    - Arbetsflöden har inbyggda e-postmeddelanden. En kund kan konfigurera meddelandena så att användarna skickar e-postmeddelanden. Dessa meddelanden resulterar inte i meddelande från åtgärdscentret för användare.
    - I en framtida uppdatering kommer vi att lägga till ett meddelande från åtgärdscenter så att en användare tilldelas en arbetsflödesuppgift. 
- Lägga till meddelanden till arbetsflöden
    - Meddelanden i åtgärdscentret kan skapas för specifika användare, t.ex. ett meddelande som skapats från ett arbets flöde i X++.
    - [Arbetsflöden har affärshändelser](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) som kunden kan använda för att utlösa flöden med de aviseringar som de letar efter.   

Sammanfattningsvis, om en användare inte får rätt meddelanden från åtgärdscentret när de tilldelas en arbetsflödesuppgift, och sedan använder [affärshändelser för arbetsflöden](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) med Microsoft Power Automate för att ge ytterligare eller andra meddelanden.

## <a name="why-is-workflow-editor-not-able-to-start-under-ad-fs"></a>Varför kan inte arbetsflödesredigeraren starta under AD FS?
När du kör under Active Directory Federation Services (AD FS) i en uppgraderad miljö kan arbetsflödesredigeraren ha problem med att starta. Om den gör det, kontrollera att URL "https://dynamicsaxworkfloweditor/" läggs till egenskapen **Microsoft Dynamics 365 for Operations lokalt - arbetsflöde - internt program** i ADFS-inställningar.

## <a name="why-am-i-getting-sql-deadlocks-on-workflow-processing"></a>Varför får jag SQL-dödlägen vid arbetsflödesbearbetning? 
Standardfältvärdet för **Antal arbetsflödesobjekt per batch** på sidan **Arbetsflödesparametrar** är 0. Värdet 0 gör att standardvärdet för 20 artiklar per batch ändras. Var försiktig när du justerar det här värdet eftersom ett stort antal poster per batch (> 40) kan orsaka dödlägen i SQL.

## <a name="what-is-the-workflow-enhanced-error-feature"></a>Vad är funktionen utökat fel i arbetsflödet?
Den utökade felfunktionen i arbetsflödet i version 10.0.13 lägger till felkoder för att skilja mellan olika klasser av arbetsflödesfel. De felmeddelanden som rapporteras är mest likvärdiga med mindre skillnader för att göra dem tydligare.
