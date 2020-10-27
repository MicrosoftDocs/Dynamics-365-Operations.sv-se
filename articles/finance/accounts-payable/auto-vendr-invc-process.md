---
title: Automatiserade processer för leverantörsfakturering – översikt
description: Det här ämnet beskriver möjligheten att automatisera bearbetning av leverantörsfaktura och fördelar med att använda en automatiserad process.
author: abruer
manager: AnnBe
ms.date: 08/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 187b3c4f1a8b2c9ec6df95c19b261756ec4562dc
ms.sourcegitcommit: 6ffbae02de2eee1f3be9bab2da37a3771aae8bec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2020
ms.locfileid: "3905035"
---
# <a name="automated-vendor-invoicing-processes-overview"></a>Automatiserade processer för leverantörsfakturering – översikt

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Det här ämnet beskriver möjligheten att automatisera bearbetning av leverantörsfaktura och fördelar med att använda en automatiserad process. Denna funktion består av funktioner som aktiveras i funktionshantering. Dessa funktioner gäller bara för leverantörsfakturor, inte för fakturor som bearbetas via sidan **Fakturajournalen** eller **Fakturaregisterjournal**.

Organisationer arbetar ofta med tredje part för att bearbeta pappersfakturor med hjälp av en OCR-tjänsteleverantör. Tjänstleverantören returnerar metadata för den maskinläsbara fakturan. Med hjälp av automatisering kan du med hjälp av funktionerna för automatisering av leverantörsreskontra använda dessa artefakter från leverantörsreskontra.

Du kan automatisera vissa faktureringsprocesser i leverantörsreskontra. Dessa processer omfattar att skicka importerade leverantörsfakturor till arbetsflödessystemet och matcha bokförda inleveransrader till pågående leverantörs fakturarader. Den automatiserade processen visar information om förloppet för en leverantörsfaktura när den förflyttas genom varje process. Den här funktionen kan hjälpa leverantörsreskontraansvariga och chefer att hantera leverantörsfakturor på ett mer effektivt sätt. Den hjälper också till att minska fel och ineffektivitet som kan uppstå när information anges och bearbetas manuellt.

Automatiseringsprocesser kan användas för att utföra dessa uppgifter:

- Skicka importerade fakturor automatiskt till arbetsflödessystemet.
- Matcha produktinleveranser mot väntande leverantörsfakturarader.
- Simulera bokföring innan en leverantörsfaktura bokförs.
- Visa arbetsflödeshistorik snabbt och effektivt.
- Visa och analysera resultaten av automatiserad bearbetning av leverantörsfakturor.

## <a name="vendor-invoice-automation--submit-imported-vendor-invoices-to-the-workflow-system"></a>Automatisering av leverantörsfaktura – skicka importerade leverantörsfakturor till arbetsflödessystemet

Som en del av en uppdelad faktureringsprocess för leverantörsreskontra kan du låta systemet automatiskt skicka in en importerad faktura till arbetsflödessystemet. Processen körs i bakgrunden med en frekvens som du anger (antingen per timme eller per dag). Möjligheten att automatiskt skicka importerade fakturor till arbetsflödessystemet kräver att processen börjar med en importerad faktura. Om du vill vara säker på att fakturan kan bearbetas från början till slut utan manuell ingrepp, måste du inkludera en automatisk bokföringsuppgift i arbetsflödeskonfigurationen.

Fakturor som är relaterade till inköpsorder och fakturor som innehåller en anskaffningskategori som inte ingår i inköpsordern och som inte finns i lager, kan automatiskt skickas till arbetsflödessystemet. Fakturor som anges manuellt och fakturor som skapas via **Arbetsyta för leverantörssamarbetesfakturering** måste manuellt skickas till arbetsflödessystemet.

Automatiseringsfunktionen tillhandahåller ett flexibelt ramverk där du kan definiera företagsspecifika regler för att skicka importerade leverantörs fakturor till arbetsflödessystemet och matcha bokförda produktinleveranser mot pågående leverantörsfakturarader.

## <a name="vendor-invoice-automation--match-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Automation av leverantörsfaktura - Matcha bokförda produktinleveranser mot fakturarader som har en policy för trevägsmatchning

Systemet kan automatiskt matcha bokförda produktinleveranser mot fakturarader som en policy för trevägsmatchning har definierats för. Processen kommer att köras tills den matchade kvantiteten för produktinleverans är lika med faktura antalet. Som en del av denna process kan du ange det maximala antalet gånger för att försöka med automatisk matchning – Välj det antal gånger som systemet ska försöka matcha produktinleveranser mot en fakturarad innan det finner att processen misslyckades. Processen kommer att köras i bakgrunden, antingen varje timme eller per dag. Du kan köra den automatiska matchningen som en del av processen för att skicka fakturor till arbetsflödessystemet. Du kan också köra den som en fristående process.

## <a name="vendor-invoice-automation--pre-validate-vendor-invoice-posting"></a>Automation av leverantörsfaktura – för validering av bokföring av leverantörsfaktura

Vid bokföringssimulering slutförs valideringsstegen som utförs under bokföringsprocessen för leverantörsfakturor, men inga konton uppdateras. Om du vill köra processen kan du välja antingen en enda faktura eller flera fakturor på sidan **Pågående leverantörsfakturor**.

## <a name="vendor-invoice-automation--enhanced-experience-for-viewing-workflow-historical-information-for-vendor-invoices"></a>Automatisering av leverantörsfaktura – förbättrad erfarenhet för visning av arbetsflödeshistorik information för leverantörsfakturor

En vy över arbetsflödeshistoriken som är lättläst för leverantörsfakturor tillhandahålls. Arbetsflödeshistorik för leverantörsfakturor kan nås direkt från leverantörsfakturan. Därför behövs det färre musklick för att hitta den informationen.

## <a name="vendor-invoice-automation--analytics-and-metrics"></a>Automatisering av leverantörsfaktura – analys och mått

Arbetsytan **Leverantörsfakturaregistrering** kan du fokusera på leverantörsfakturor som inte har gjort dem via den automatiska processen. Sida vid sida på arbetsytan visar information om leverantörsfakturor som inte kunde skickas till arbetsflödessystemet, importeras eller matchas mot produktinleveranser. Microsofts Power BI mätvärden ges också för att ge leverantörsreskontra chefer insikt i effektiviteten vid automatisering av leverantörsfakturor.
