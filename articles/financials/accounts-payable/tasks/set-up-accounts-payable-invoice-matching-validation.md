---
title: Ställ in validering av fakturamatchning för leverantörsreskontra
description: I den här registreringen används demonstrationsföretaget USMF.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a26a057b524f162e4b288b88e8c30f7c5db7a45
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "346857"
---
# <a name="set-up-accounts-payable-invoice-matching-validation"></a>Ställ in validering av fakturamatchning för leverantörsreskontra

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här registreringen används demonstrationsföretaget USMF. Leverantörsreskontrachefsrollen eller redovisningschefsrollen ska utföra stegen nedan. Innan du börjar kontrollerar du att konfigurationsnyckeln för fakturamatchning har valts. Om din juridiska person spårar utgifter, till exempel frakt, genom att använda avgifter, se till att Konfigurationsnycklar för Tillägg har valts.  Fakturamatchning i leverantörsreskontra är den process där information om leverantörsfaktura, inköpsorder och produktinleverans matchas. Skillnader mellan dessa dokument kallas för matchningsavvikelser. Matchningsavvikelser jämförs med toleranserna som ställts in. Om en matchningsavvikelse överskrider toleransprocenten eller toleransmängden visas matchningsavvikelseikoner på sidan Leverantörsfaktura och på sidan Fakturahistorik och matchningsuppgifter.

1. Gå till Leverantörsreskontra > Inställningar > Parametrar för leverantörsreskontra.
2. Klicka på fliken Fakturavalidering.
3. Markera eller avmarkera kryssrutan Aktivera fakturamatchningsvalidering.
    * Välj om godkännande ska krävas innan du bokför en faktura som innehåller fakturamatchningsavvikelser. Om det anges om du vill tillåta med varning, kommer den visuella indikationen på se när avvikelser för fakturamatchning överskrider toleransen. Om du att kunna i stånd till att bokföra fakturan. Kontrollera att stolpefakturan med diskrepansfältet anges om du vill tillåta att undvika med varning måste godkänna gånger ska användas tillsammans med arbetsflöden fakturamatchningvalidering.  
    * Välj om du vill matcha ska utföras automatiskt vid fakturadatapost av systemet automatiskt i fältet om status för att matcha för uppdaterafakturahuvudet. Rekommenderat ange är Ja, om du inte datapostprestandabekymmer upplever. När du avaktiverar automatiska uppdateringar kan aktivera snabbare, eftersom systemets prestanda fakturamatchningvalideringen ska kopplas efter vid inmatning. Datapostkontoristen måste uppdatera manuellt fakturans matchstatusen för att se fakturamatchningvalideringresultaten, när den inte anges till.  
4. Växla utökningen av avsnittet Matchning av fakturasummor.
5. Markera eller avmarkera kryssrutan Matchning av fakturasummor för att matcha verkliga fakturasummor med förväntade summor.
    * Välj om en ikon ska visas om avvikelser för fakturamatchning överskrider toleransen. Du kan välja att visa ikonen när en positiv diskrepans överskrider toleransen, eller när antingen en positiv eller negativ diskrepans överskrider toleransen.  
    * Toleransen är till exempel 5 procent och det totala fakturabeloppet på inköpsordern är 100,00. Därför visas en prismatchningsikon om det totala fakturabeloppet på fakturan överstiger 105.00. Om du väljer Om större eller mindre än tolerans, visas också en ikon om fakturabeloppet är mindre än 95,00.  
6. Ange ett nummer i fältet Toleransprocent för fakturasummor.
7. Växla utökningen av avsnittet Pris- och kvantitetsmatchning.
    * Välj ett värde som ska användas som standardpolicy för den juridiska person som du arbetar med i fältet Radmatchningspolicy. Ej ”kräver” innebär att det inte finns någon verifiering av enskilda fakturaradspriser till inköpsorderpris- eller fakturakvantiteter till obligatoriska följesedelns kvantiteter. ”Tvåvägsmatchning” betyder att verifieringen med fakturarader krävs men endast inköpsordern och leverantörens fakturadokumenten ingår i verifieringen. Produktinleveransen faktorer inte till de matcha de valideringar. ”Trevägsmatchning” betyder att fakturans nettoenhetspris ska jämföras med inköpsorderns netto enhetspris och matcha den produktinleveranskvantiteten ska jämföras med kvantiteten.  
    * Om du använder en rad matchningspolicy av tvåvägs matcha eller trevägsmatcha, kan du ange procentsatser för pristoleranser för dina juridisk person, artiklar och leverantörer på sidan för artikel pristolerans. När leverantörsfakturor jämförs med informationen i inköpsorder görs en sökning efter tillämpliga toleransprocentsatser.  
8. Välj ett alternativ i radmatchningspolicyfältet.
    * Om du vill tillåta en annan matchningsnivå för en artikel, leverantör, leverantör och artikel i kombination eller en inköpsorderrad, väljer du ett värde i fältet Tillåt åsidosättning av matchningspolicy. Radmatchningspolicyn för den juridiska personen kan åsidosättas för en specifik leverantör, artikel eller kombination av leverantör och artikel på matchningspolicysidan.  
    * Välj ett värde i fältet Matcha prissummor för att matcha prissummor för radartiklar på fakturor. Den här typen av att de är praktiskt, när leverantören skickar flera fakturor för samma inköpsorderraden. Du kan jämföra prisinformation för nettobeloppet för varje rad på fakturan, och alla väntande och tidigare bokförda fakturarader, med nettobeloppet för den motsvarande inköpsorderraden.  
9. Välj ett alternativi fältet Matcha prissummor.
10. Ange ett nummer i fältet Tolerans för inköpsprissumma.
11. Växla utökningen av avsnittet Avgiftsmatchning.
12. Markera kryssrutan Matcha avgifter om du vill matcha verkliga transaktioner mot förväntade kostnader.
13. Stäng sidan.

