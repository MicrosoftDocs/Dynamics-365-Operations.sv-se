---
title: "Produktinleverans mot inköpsorder"
description: "Den här artikeln innehåller en beskrivning av olika alternativ för att registrera produkter som mottagna."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PurchTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 93113
ms.assetid: d4ec3e86-fce2-4546-911b-e0acf64c8887
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 1c8143ec9b18bf95d7cc10f966ce00e5a398a147
ms.lasthandoff: 03/31/2017


---

# <a name="product-receipt-against-purchase-orders"></a>Produktinleverans mot inköpsorder

Den här artikeln innehåller en beskrivning av olika alternativ för att registrera produkter som mottagna.

Produktinleverans är en process som används för att registrera att de produkter som har beställts har tagits emot så att inköpsorderrader (IO) sedan kan bearbetas för fakturering. I vissa fall genomgår produkterna en förregistrering där extra information från leverantören registreras innan produkterna tas emot. När en produkt tas emot får den först statusen **Registrerad**. Produkten kan sedan genomgå ytterligare processer, till exempel kvalitetshantering, innan den slutligen får statusen **Mottagen**.

## <a name="preregistration-asn"></a>Förregistrering (ASN)
Leverantörer kan dela information om produkter som ska levereras. I det här fallet kan du förregistrera produkten om du vill registrera den här informationen innan produkten tas emot. Genom att förregistrera produkten minskar du mängden arbete som krävs vid registrering av artikel och inleverans. Leverantörer kan tillhandahålla produktinformation elektroniskt via en leveransavisering (ASN) som sedan automatiskt registreras i systemet. Informationen i ASN omfattar kvantiteten på de produkter som ska levereras och leveransdatumet. ASN kan även innehålla information såsom batch- eller serienummer. Registrering av ASN sker i modulen **Transporthantering**.

## <a name="registration"></a>Registrering
Registreringen av produktinleveransen sker ofta vid inlastningsplatser på ett lagerställe. Den utförs antingen med hjälp av en handenhet eller via införseljournaler. Du kan även registrera produktinleveransen manuellt med hjälp av åtgärden **Registrering** på sidan **Inköpsorder**. I båda fallen markeras produkten som **Registrerad**. Observera att produkten ännu inte har statusen **Mottagen**.  

Produkter som tas emot på ett lagerställe kan genomgå en kvalitetskontroll innan de placeras på lagret. Kvalitetsorder eller karantänorder kan användas för att utföra kvalitetskontrollen. Om en kvalitetsorder används kan du konfigurera processen för att tillfälligt blockera produkter genom en reservation medan de kontrolleras. Om en karantänorder används flyttas produkterna till ett annat lagerställe för kontroll. Det här lagerstället kallas karantänlagerställe. I båda kvalitetskontrollsprocesserna kan vissa produkter komma att kasseras, antingen för att de inte uppfyller förväntningarna på kvalitet eller på grund av att kvalitetskontrollen innefattar destruktiv provning av ett urval av produkten.

## <a name="product-receipt"></a>Produktinleverans
Oftast används åtgärden **Produktinleverans** på sidan **Inköpsorder** för att markera produkten som **Mottagen** på inköpsordern. Sidan **Bokföra produktinleverans** har olika alternativ för den kvantitet som redovisas som mottagen. Du kan till exempel ställa in fältet **Kvantitet** till **Orderkvantitet** eller **Inleverera nu-kvantitet**. Om ett lagerställes inleveransprocess har använts är det vanligt att fältet i stället ställs in till **Registrerad kvantitet**. Du kan ändra kvantiteterna för varje orderrad som kommer att få statusen **Mottagen** för att kunna ta hänsyn till eventuella avvikelser såsom under- eller överleverans. Vid produktinleveransen måste du ange en identifierare för produktinleveransen. Identifieraren utgörs vanligtvis av en referens till följesedeln från leverantören. Den här identifieraren krävs för redovisning eftersom den möjliggör kontroller och granskningar av leverantörens följesedlar mot vad som har tagits emot. Den krävs även för det bokförda lagret och utgiften.  

Om en medarbetare beställde varor med hjälp av en inköpsrekvisition kan den anställde bli ombedd att bekräfta mottagandet av produkten. Du kan konfigurera det här scenariot med hjälp av ett arbetsflöde. Du kan konfigurera arbetsflödesvillkor så att de matchar din affärsprocess.  

Inköpsorder kan skapas för produkter som inte är avsedda som lagervaror, men som betraktas som en utgift. Den här kategorin inkluderar orderrader där produkter får statusen **Finns inte i lager** av respektive lagermodellgrupp och även rader som använder anskaffningskategorier. I detta fall kan artiklarna inte genomgå ankomstregistrering och inleveransen på lagerstället. I stället används åtgärden **Produktinleverans** för att registrera inleveransen direkt på inköpsordern och inleveransen baseras då på den beställda kvantiteten och inte på den registrerade kvantiteten.  

Du kan skapa inköpsorderrader där alternativet **Ny anläggningstillgång** är aktiverat. Det här alternativet visar att inköpet bör betraktas som en anläggningstillgång i stället för en lagertillgång. I det här fallet har reglerna för bestämning av anläggningstillgångar konfigurerats till att fastställa om inköpet av produkten eller kategorin överskrider vissa tröskelvärden och måste därmed redovisas som en tillgång och genomgå hanteringen av anläggningstillgången. Inköp kan också göras mot en befintlig anläggningstillgång. I det här fallet justeras beloppet vid behov.  

Du kan välja flera order och bearbeta inleverans på alla order tillsammans. Denna metod används inte ofta, men du kanske vill använda den om en leverantör har slagit ihop leveranserna till dig i en enda last. Det finns en funktion för att göra samlingsuppdateringar vid produktinleverans av inköp. Du kan bokföra en enstaka följesedel från leverantören för mer än en inköpsorder med hjälp av samlingsuppdateringar.  

Inköpsorder kan skapas från en försäljningsorder om alternativet **Direktleverans** har valts. När du använder direktleverans tas produkterna inte emot på lagerstället utan skickas direkt från leverantören till kunden. I detta fall registreras vanligtvis inleveransen direkt på inköpsordern. Inleveransen kan utföras automatiskt, till exempel genom elektroniskt datautbyte (EDI) med leverantören. Om inköpsordern är en koncernintern inköpsorder är det även möjligt att låta Microsoft Dynamics 365 for Operations att automatisera inleveransen av den koncerninterna försäljningsordern vid leverans. När du använder direktleverans redovisas produkterna fortfarande som en lagertillgång, även om de inte anländer fysiskt till lagerstället. När produktinleveransen registreras på inköpsordern uppdateras därför försäljningsordern automatiskt med en följesedel så att den totala förändringen i lagret är lika med 0 (noll). Vid direktleveranser bör du inte kräva förregistrering. Om du använder lagerställen som är aktiverade för lagerstyrning kan du kringgå kravet på registrering av ID-numret genom att ange ett virtuellt lagerställe. Du specificerar det här lagerstället i fältet **Lagerställe för direktleverans** på produkten. 

När produktinleveransen har bearbetats på Inköpsordern, IO-status anges som **mottagna** att visa att fakturan kan behandlas för ordern. Du kan granska uppgifter om produkter som redan har tagits emot med hjälp av sidan **Produktinleveransjournaler**.  

Du kan komma åt den här sidan från åtgärdsgruppen **Inleverans** på sidan **Inköpsorder**. Informationen i journalerna omfattar uppgifter om kvantiteter, datum och dimensioner.

<a name="see-also"></a>Se även
--------

[Purchase order overview](purchase-order-overview.md)

[Purchase order creation](purchase-order-creation.md)

[Godkänna och bekräfta inköpsorder](purchase-order-approval-confirmation.md)

[Översikt över leverantörsfakturor](/dynamics365/operations/financials/accounts-payable/vendor-invoices-overview)


