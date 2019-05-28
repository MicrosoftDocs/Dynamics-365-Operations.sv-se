---
title: Momsåtervinning i Utgiftshantering
description: Det här avsnittet beskriver hur du tar emot återbetalningar vid berättigade momstransaktioner.
author: saraschi2
manager: AnnBe
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPerDiems
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8bc9e533de40aa8fe8ddfe422cfe0f4078a360c7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568950"
---
# <a name="vat-recovery-in-expense-management"></a>Momsåtervinning i Utgiftshantering

[!include [banner](../includes/banner.md)]

För att få återbetalningar vid berättigade momstransaktioner måste ett företag eller en organisation identifiera, samla in, kontrollera och skicka korrekt information. Den här processen omfattar flera aktiviteter och beroende på företagets storlek kan det innefatta flera medarbetare eller roller.

Om du vill återställa moms med utgiftshantering måste följande förutsättningar uppfyllas:

- Momskoder måste skapas för länder/regioner som tilldelats utgiftskategorier.
- En momsgrupp måste skapas för varje momskod.
- En artikelmomskod måste skapas för varje artikelmomsgrupp.

När förutsättningarna är klara följer medarbetarna dessa steg för att begära återbetalning för momstransaktioner.

1. På en utgiftsrapport ange momsinformation om kreditkortstransaktioner för att identifiera berättigade momsåterbetalningar.
2. Kontrollera att all momsinformation har slutförts och bokför sedan utgiftsrapporten.
3. Behandla utgifter som berättigar till internationell momsåtervinning.
4. Skicka momsåtervinningsdata till tredje partsleverantör för att ansöka om internationella momsåterställningsreturer.
5. Bearbeta utgifter för inhemsk momsåtervinning.

Följande avsnitt innehåller exempel som visar hur Contoso-medarbetare slutför varje steg.

## <a name="on-an-expense-report-enter-tax-information-about-credit-card-transactions-to-identify-eligible-vat-refunds"></a>På en utgiftsrapport ange momsinformation om kreditkortstransaktioner för att identifiera berättigade momsåterbetalningar.

Nancy, en Contoso-säljare som är hemmahörande i USA återvände nyligen från en försäljningsresa till Storbritannien. Under resan uppkom vissa personliga kreditkortsutgifter för måltider. Nancy måste nu skapa en utgiftsrapport för att stämma av sina utgifter.

När Nancy anger information i sin utgiftsrapport kan hon välja **Storbritannien** i fältet **land/region** på sidan **Redigera utgiftsrapport**. Lista över momsgrupper filtreras sedan så att den endast visar de grupper som gäller för Storbritannien. Nancy markerar momsgruppen **Storbritannien 001** och väljer sedan artikelmomsgruppen **Måltider**. Sedan lägger hon till en ny transaktion för sitt boende. Eftersom det endast finns en momsgrupp och artikelmomsgrupp för logi i Storbritannien fylls denna information i automatiskt i Nancys utgiftsrapport.

Alla utgifter per Contosos policy måste ha ett matchande kvitto. Därför får Nancy när hon sparar sin utgiftsrapport ett meddelande om att hon måste bifoga ett kvitto för varje transaktion som hon anger på utgiftsrapporten. Nancy kontrollerar att hon har bifogat en digital bild av varje transaktionskvitto till sin utgiftsrapport och skickar sedan rapporten för godkännande. Hon skickar sedan papperskvitton till bearbetning av backoffice-teamet. Detta team skickar momsåtervinningsdata till tredje parts återförsäljare som ansöker om internationell momsåtervinning för Contoso-teamet.

## <a name="make-sure-that-all-tax-information-is-complete-and-then-post-the-expense-report"></a>Kontrollera att all momsinformation har slutförts och bokför sedan utgiftsrapporten.

April, Contosos leverantörsreskontrakoordinator måste ange all momsinformation som saknas i en utgiftsrapport innan rapporten kan bokföras. Hon öppnar sidan **Utgiftsrapportsinformation** och ser Nancys godkända utgiftsrapport. April öppnar sedan utgiftsrapporten för att visa information om transaktionerna. Hon ser att Nancy inte anger en artikelmomsgrupp för en av transaktionerna. Eftersom den här informationen inte tillhandahålls kan April inte bokföra utgiftsrapporten. Därför tittar April på sidan **Momskonfigurationer** i Utgiftshantering och hittar lämpliga artikelmomsgrupper för land/region och transaktionstypen. April kan nu bokföra utgiftsrapporten i redovisningen.

När April bokför utgiftsrapporten, skapas en momsåtervinningsbara arbetsuppgift. Arbetsuppgiften tilldelats en medlem av backoffice-bearbetningsteamet. April får ett meddelande som bekräftar att bokföringen lyckades. Meddelandet visar också hur många momstransaktioner som har identifierats för återvinning.

## <a name="process-expenses-that-are-eligible-for-international-vat-recovery"></a>Behandla utgifter som berättigar till internationell momsåtervinning.

Arnie, en medlem av Contosos backoffice-bearbetningsteam, ansvarar för att bekräfta att all nödvändig information för momsåtervinning är inkluderad i utgiftsrapporter. Han öppnar sidan **Momsåterbetalning för utgift** och väljer utgiftsrapporten som Nancy skickat. Arnie verifierar att alla kvitton som krävs är bifogade och att rätt moms och momskoder angavs.

När Arnie mottar papperskvittona från Nancy kontrollerar han papperskvittona mot de digitala kvittona och ändrar status för utgiftsrapporten till **Klar för återbäring**.

## <a name="send-vat-recovery-data-to-the-third-party-vendor-to-file-international-recovery-returns"></a>Skicka momsåtervinningsdata till tredje partsleverantör för att ansöka om internationella momsåterställningsreturer.

När Arnie är redo att skicka utgiftsrapportdata till tredje parts återförsäljare som ska ansöka om momsåtervinning öppnar han sidan **Momsåterbetalning för utgift**. Han filtrerar sidan så att den visar de utgiftsrapporter som är markerade som **klar för återbäring**. Arnie väljer sedan **Fil**&gt;**Exportera till Excel**. Momsinformationen från utgiftsrapport exporteras till ett Microsoft Excel-kalkylblad. Arnie skickar kalkylbladet till tredje partsleverantören och inkluderar ett meddelande om att papperskvittona har skickats via bud.

## <a name="process-expenses-for-domestic-vat-recovery"></a>Bearbeta utgifter för inhemsk momsåtervinning.

Arnie måste kontrollera att transaktionerna i utgiftsrapporten är berättigade för momsåtervinning och att digitala kvitton har bifogats till rapporterna. För att börja bearbeta berättigade utgifter för inhemsk återvinning öppnar Arnie sidan **Momsåterbetalning för utgift** och väljer utgiftsrapporten som kräver verifiering. Han kontrollerar att kvittona är i företagets namnet i stället för medarbetaren. För momsåtervinning måste kvittona vara i företagets namn. Arnie bekräftar sedan att rätt momsgrupp och momskoder har tillämpats.

När Arnie får papperskvittona kan han ändras status för utgiftsrapporten till **klar för återbäring**. Han kan sedan ansöka om återvinningen från lämplig skattemyndighet. I det här fallet är lämplig skattemyndighet i USA Internal Revenue Service (IRS).
