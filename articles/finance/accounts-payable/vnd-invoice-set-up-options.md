---
title: Konfigurera alternativ för automatisering av leverantörsfakturor (förhandsversion)
description: I den här artikeln beskrivs de alternativ som är tillgängliga när du ställer in och konfigurerar automatisering av leverantörsfakturor.
author: sunfzam
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 86ad68b3dc08bf2c57ab5f9bc6c65bc37c0901e6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874853"
---
# <a name="setup-options-for-vendor-invoice-automation"></a>Konfigurera alternativ för automatisering av leverantörsfakturor

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs de alternativ som är tillgängliga när du ställer in och konfigurerar automatisering av leverantörsfakturor. I funktionerna för fakturaautomatisering används följande typer av installationsparametrar:

- Parametrar för automatisk tillämpande av förskottsbetalningar på importerade fakturor.
- Parameter för att skicka importerade leverantörsfakturor till arbetsflödessystemet och matcha bokförda inleveransrader till pågående leverantörs fakturarader
- Parametrar för bakgrundsuppgifter för processautomatisering. Ramverket för processautomatiseringen används för att skicka importerade leverantörsfakturor till arbetsflödessystemet. Den används också för att automatiskt matcha bokförda produktinleveranserrader mot pågående leverantörsfakturarader och utföra fakturamatchningsvalidering för manuella fakturor som har matchats automatiskt mot produktinleveransrader. Olika affärsprocesser använder det här ramverket för att definiera hur ofta den valda processen körs. De tillgängliga frekvenserna för **matcha produktinleverans till fakturarader** och bakgrundsprocesser **skicka in leverantörsfakturor till arbetsflödet** omfattar **timmar** och **dagar**.

Om du vill ställa in eller visa information om en bakgrundsaktivitet går du till **Systemadministration \> Installation \> Processautomatisering** och fliken **Bakgrundsaktivitet**.

Om du vill ha en nedrullad automatisering från importprocessen genom bokföringen av leverantörsfakturan måste du skapa ett arbetsflöde för leverantörsfakturan. För att ställa in ett arbetsflöden, gå till **Leverantörsreskontra > Inställningar > Arbetsflöden för leverantörsreskontra**. Om du vill vara säker på att fakturan kan bearbetas från början till slut utan manuell ingrepp, måste du inkludera en automatisk bokföringsuppgift i arbetsflödeskonfigurationen.

## <a name="parameters-for-automatically-applying-prepayments-in-imported-invoices"></a>Parametrar för automatisk tillämpande av förskottsbetalningar på importerade fakturor

- **Tillämpa automatiskt förskottsbetalning för importerade fakturor** – När det här alternativet ställs in på **Ja**, söker systemet automatiskt efter befintliga förskottsbetalningar för en motsvarande inköpsorder när leverantörsfakturor importeras. Om det finns förskottsbetalningar som kan användas läggs en extra rad till för att tillämpa förskottsbetalningarna på de leverantörsfakturor som importeras.
- **Blockera uppföljande automationsprocess om ansökningen om förskottsbetalning inte kan användas** – När det här alternativet ställs in på **Ja**, spärras fakturor om en förskottsbetalning inte kan användas. Liksom andra automatiserade processer, såsom kvittomatchningsprocessen och inlämning till en arbetsflödesprocess, kommer faktura automatiseringsprocessen inte att ta upp blockerade fakturor förrän förskottsbetalningen tillämpas manuellt. 

## <a name="parameters-for-submitting-imported-vendor-invoices-to-the-workflow-system"></a>Parametrar för att skicka importerade leverantörsfakturor till arbetsflödessystemet

Specifika parametrar används för att skicka importerade leverantörsfakturor till arbetsflödessystemet. Dessutom används vissa parametrar för att matcha bokförda produktinleveranser mot pågående leverantörsfakturarader. På fliken **Automation av leverantörsfaktura** på sidan **Parametrar för leverantörsreskontra**, är de parametrar som du måste ställa in uppdelade mellan följande avsnitt:

- Arbetsflöde över leverantörsfakturor
- Matcha produktinleveranser automatiskt

Följande parametrar är tillgängliga:

- **Skicka automatiskt importerade fakturor till arbetsflöde** – om du ställer in det här alternativet på **Ja** skickas importerade fakturor automatiskt till arbetsflödessystemet. Om det här alternativet är inställt på **Nej**, måste fakturorna skickas manuellt. Genom att ställa in detta alternativ på **Ja** aktiverar du en beröringslös process från importresultaten genom bokföring.

    Du kan ställa in det här alternativet på **Ja** endast om ett aktivt arbetsflöde för en leverantörsfaktura har ställts in för din juridiska person. För att ställa in ett arbetsflöden, gå till **Leverantörsreskontra \> Inställningar \> Arbetsflöden för leverantörsreskontra**.

- **Matcha produktinleveranser mot fakturarader innan de skickas automatiskt** – om du ställer in det här alternativet på **Ja**, kan den importerade fakturan inte automatiskt skickas till arbetsflödessystemet förrän den matchade produktinleveransen är lika med den fakturerade kvantiteten. Genom att ställa in detta alternativ på **Ja** kan du aktivera automatisk matchning av bokförda produktinleveranser på fakturarader som en tresiffrig matchningsprincip har definierats för. Den processen kommer att köras tills den matchade kvantiteten för produktinleverans är lika med faktura antalet. Vid den tidpunkten skickas fakturan automatiskt till arbetsflödessystemet.

    Alternativet **matcha produktinleveranser mot fakturarader före automatisk sändning** är endast tillgängligt om alternativet **Aktivera validering av fakturamatchning**. När det här alternativet väljs markeras alternativet **Matcha produktinleveranser automatiskt till fakturarader** automatiskt.

- **Kräv att de beräknade summorna ska vara lika med de importerade summorna för automatisk arbetsflödessändning** – om du ställer in det här alternativet på **Ja**, kan fakturan inte automatiskt skickas till arbetsflödessystemet förrän summorna som beräknas för fakturan är lika med de importerade summorna. Om det här alternativet är inställt på **Nej** kan fakturan automatiskt skickas till arbetsflödessystemet, men den kan inte bokföras förrän de beräknade summorna korrigeras så att de matchar de importerade summorna. Om du inte importerar fakturabeloppet eller momsbeloppet ska det här alternativet ställas in på **Nej**.
- **Matcha automatiskt produktinleveranser mot fakturarader** – om du ställer in det här alternativet på **Ja** kan bakgrundsbearbetningen användas för automatisk matchning av bokförda produktinleveranser på fakturarader som en tresiffrig matchningsprincip definieras för. Processen kommer att köras tills den matchade kvantiteten för produktinleverans är lika med fakturaantalet, eller tills värdet av fältet **antal gånger som ett nytt matchande** har nåtts. Processen kan köras tills fakturan har skickats till arbetsflödessystemet.

    Det här alternativet är endast tillgängligt om alternativet **Aktivera fakturamatchningsvalidering** har valts.

    Om du ställer in **matcha produktinleveranser mot fakturarader innan alternativet för automatisk matchning** till **Ja**, kan det här alternativet inte ställas in på **Nej**. Om du ställer in det här alternativet på **Nej** måste du först ange alternativet **matcha produktinleveranser mot fakturarader innan alternativet för automatisk matchning** till **Nej**.

- **Antal gånger för att försöka med automatisk matchning** – Välj det antal gånger som systemet ska försöka matcha produktinleveranser mot en fakturarad innan det finner att processen misslyckades. När det angivna antalet försök har nåtts tas fakturan bort från automatiseringsbearbetningen.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
