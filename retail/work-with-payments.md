---
title: Betalningsmetoder i ett Callcenter
description: "Det här avsnittet ger en beskrivning av olika betalningsmetoder du kan använda i en kundtjänst i Butik och handel."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 636d83ecc7732a164924352853603588cded0db4
ms.lasthandoff: 03/31/2017


---

# <a name="payment-methods-in-a-call-center"></a>Betalningsmetoder i ett Callcenter

Det här avsnittet ger en beskrivning av olika betalningsmetoder du kan använda i en kundtjänst i Butik och handel.

Betalningsmetoderna som används i andra kanaler i Butik och handel i Microsoft Dynamics AX såsom kontanter, checkar, kreditkort och presentkort kan även användas i kundtjänster. När du har ställt in en betalningsmetod för en kundtjänst visas den som ett alternativ i avsnittet **Betalningar** på sidan **Försäljningsorder** för kundtjänstanvändare. Dessutom kan du kan ställa in kuponger om du vill erbjuda rabatter till kunder när de gör en beställning hos ditt företags kundtjänst. Kuponger kan antingen gälla för en fast beloppsrabatt eller för en procentsats av ett artikelpris eller den totala ordersumman. En värdekupong kan till exempel erbjuda kunderna en rabatt på 75,00 kronor när kunden spenderar 750,00 kronor eller mer. Du kan skapa olika typer av kuponger, ställa in överordnade/underordnade kuponger och kopiera eller annullera en kupong. Använd alternativen i följande tabell för att skapa kuponger.

|                           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Attribut**             | Ange värdet för kupongens förväntade återköptspris som en procentsats i fältet **Återköpspris** och välj sedan om kupongen ska användas som en engångskupong, en kupong som automatiskt kommer att återutfärdas eller om den är specifik för en kund.                                                                                                                                                                                                                                                                                                                                                                                       |
| **Giltig**                 | Ange datumen för den första och sista dagen då kupongen är giltig i fälten **Startdatum** och **Slutdatum**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Inkludera/exkludera regler** | Välj om några kataloger eller artiklar inkluderas eller exkluderas i kupongen i fälten **Kataloger** och **Artiklar**. Om du väljer **Inkludera** eller **Utesluta**ska du klicka på **Ställ in** och välja **Inkludera/uteslut kataloger** eller **Inkludera/uteslut produkter** och ange information om katalogen eller artikeln. Om du väljer **Inga** i dessa fält inkluderas alla kataloger eller artiklar i kupongen.                                                                                                                                                                                                                          |
| **Diverse**         | Om den här kupongen inte ska gå att använda tillsammans med andra rabatter, välj kryssrutan **Uteslut**. Välj sedan var kupongen kan användas i fältet **Ursprung**. Markera kryssrutan **Tillverkarkupong** om det här är en tillverkares kupong.                                                                                                                                                                                                                                                                                                                                                                |
| **Framtida kupong**         | Om den här kupongen ska kopplas till andra kuponger som en överordnad kupong markerar du kryssrutan **Överordnad kupong**. Om den här kupongen ska kopplas till en befintlig kupong som en underordnad kupong, välj den överordnade kupongen i fältet **ID för överordnad kupong**. Du kan till exempel skapa en kupong för nästkommande vårkatalog. Alla andra kuponger du skapar för vårkatalogen blir underordnade kuponger till vårkatalogkupongen. Underordnade kuponger kan omfatta en rabatt på 20 procent för nya kundorder, en rabatt på 10 procent på en nylanserad artikel eller en rabatt på 95,00 kronor för order som överstiger 1 000,00 kronor. |

Om du skickar in en kreditkortsbetalning från sidan **Försäljningsorder** och får ett meddelande om att kortet inte godkändes kan du hantera godkännandet manuellt. Du kan godkänna, avvisa eller skicka om en kreditkortstransaktion med hjälp av sidan **Auktoriseringshantering**. Du kan använda sidan Kundtjänstparametrar för att konfigurera fler betalningsbearbetningsalternativ:

-   Checkspärrar gör att ekonomipersonal kan bearbeta order som har spärrats på grund av att en check användes som betalningsmetod och att tröskelvärdet för checkspärren överskreds. Spärren kan upphävas manuellt eller upphöra automatiskt i slutet av den konfigurerade perioden.
-   Du kan ställa in trösklar över vilka återbetalningar som utfärdas via checkar och kreditkort måste godkännas manuellt. Alla återbetalningar som överskrider tröskelbeloppet läggs till i godkännandekön. När du har godkänt återbetalningen kan returförsäljningsordern faktureras.



