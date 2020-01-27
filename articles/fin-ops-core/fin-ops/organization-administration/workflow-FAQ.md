---
title: Vanliga frågor om arbetsflöde
description: Detta avsnitt besvarar några vanliga frågor om arbetsflödessystemet.
author: ChrisGarty
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cdddd26a662e9334f6d3c9806871df5b58ec03c7
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934919"
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

## <a name="workflow-editor-has-trouble-starting-under-adfs"></a>Arbetsflödesredigeraren har problem med att starta under ADFS 
När du kör under Active Directory Federation Services (AD FS) i en uppgraderad miljö kan arbetsflödesredigeraren ha problem med att starta. Om den gör det, kontrollera att URL "https://dynamicsaxworkfloweditor/" läggs till egenskapen **Microsoft Dynamics 365 for Operations lokalt - arbetsflöde - internt program** i ADFS-inställningar.
