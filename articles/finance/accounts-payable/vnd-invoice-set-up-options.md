---
title: Konfigurera alternativ för automatisering av leverantörsfakturor (förhandsversion)
description: I det här avsnittet beskrivs de alternativ som är tillgängliga när du ställer in och konfigurerar automatisering av leverantörsfakturor.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
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
ms.openlocfilehash: ebab41d8b7697f20095d6d4654718b88c8b08a82
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665208"
---
# <a name="setup-options-for-vendor-invoice-automation"></a>Konfigurera alternativ för automatisering av leverantörsfakturor

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs de alternativ som är tillgängliga när du ställer in och konfigurerar automatisering av leverantörsfakturor. I funktionerna för fakturaautomatisering används följande typer av installationsparametrar:

- Parameter för att skicka importerade leverantörsfakturor till arbetsflödessystemet och matcha bokförda inleveransrader till pågående leverantörs fakturarader
- Parametrar för bakgrundsuppgifter för processautomatisering. Ramverket för processautomatiseringen används för att skicka importerade leverantörsfakturor till arbetsflödessystemet. Den används också för att automatiskt matcha bokförda produktinleveranserrader mot pågående leverantörsfakturarader och utföra fakturamatchningsvalidering för manuella fakturor som har matchats automatiskt mot produktinleveransrader. Olika affärsprocesser använder det här ramverket för att definiera hur ofta den valda processen körs. De tillgängliga frekvenserna för **matcha produktinleverans till fakturarader** och bakgrundsprocesser **skicka in leverantörsfakturor till arbetsflödet** omfattar **timmar** och **dagar**.

Om du vill ställa in eller visa information om en bakgrundsaktivitet går du till **Systemadministration \> Installation \> Processautomatisering** och fliken **Bakgrundsaktivitet**.

Om du vill ha en nedrullad automatisering från importprocessen genom bokföringen av leverantörsfakturan måste du skapa ett arbetsflöde för leverantörsfakturan. För att ställa in ett arbetsflöden, gå till **Leverantörsreskontra > Inställningar > Arbetsflöden för leverantörsreskontra**. Om du vill vara säker på att fakturan kan bearbetas från början till slut utan manuell ingrepp, måste du inkludera en automatisk bokföringsuppgift i arbetsflödeskonfigurationen.

## <a name="parameters-for-submitting-imported-vendor-invoices-to-the-workflow-system"></a>Parametrar för att skicka importerade leverantörsfakturor till arbetsflödessystemet

Specifika parametrar används för att skicka importerade leverantörsfakturor till arbetsflödessystemet. Dessutom används vissa parametrar för att matcha bokförda produktinleveranser mot pågående leverantörsfakturarader. På fliken **Automation av leverantörsfaktura** på sidan **Parametrar för leverantörsreskontra**, är de parametrar som du måste ställa in uppdelade mellan följande avsnitt:

- Arbetsflöde över leverantörsfakturor
- Matcha produktinleveranser automatiskt

Följande parametrar är tillgängliga:

- **Skicka automatiskt importerade fakturor till arbetsflöde** – om du ställer in det här alternativet på **Ja** skickas importerade fakturor automatiskt till arbetsflödessystemet. Om det här alternativet är inställt på **Nej**, måste fakturorna skickas manuellt. Genom att ställa in detta alternativ på **Ja** aktiverar du en beröringslös process från importresultaten genom bokföring.

    Du kan ställa in det här alternativet på **Ja** endast om ett aktivt arbetsflöde för en leverantörsfaktura har ställts in för din juridiska person. För att ställa in ett arbetsflöden, gå till **Leverantörsreskontra \> Inställningar \> Arbetsflöden för leverantörsreskontra**.

- **Matcha produktinleveranser mot fakturarader innan de skickas automatiskt** – om du ställer in det här alternativet på **Ja**, kan den importerade fakturan inte automatiskt skickas till arbetsflödessystemet förrän den matchade produktinleveransen är lika med den fakturerade kvantiteten. Genom att ställa in detta alternativ på **Ja** kan du aktivera automatisk matchning av bokförda produktinleveranser på fakturarader som en tresiffrig matchningsprincip har definierats för. Den processen kommer att köras tills den matchade kvantiteten för produktinleverans är lika med faktura antalet. Vid den tidpunkten skickas fakturan automatiskt till arbetsflödessystemet.

    Alternativet matcha produktinleveranser mot fakturarader före automatisk sändning är endast tillgängligt om alternativet **Aktivera validering av fakturamatchning**. När det här alternativet väljs markeras alternativet **Matcha produktinleveranser automatiskt till fakturarader** automatiskt.

- **Kräv att de beräknade summorna ska vara lika med de importerade summorna för automatisk arbetsflödessändning** – om du ställer in det här alternativet på **Ja**, kan fakturan inte automatiskt skickas till arbetsflödessystemet förrän summorna som beräknas för fakturan är lika med de importerade summorna. Om det här alternativet är inställt på **Nej** kan fakturan automatiskt skickas till arbetsflödessystemet, men den kan inte bokföras förrän de beräknade summorna korrigeras så att de matchar de importerade summorna. Om du inte importerar fakturabeloppet eller momsbeloppet ska det här alternativet ställas in på **Nej**.
- **Matcha automatiskt produktinleveranser mot fakturarader** – om du ställer in det här alternativet på **Ja** kan bakgrundsbearbetningen användas för automatisk matchning av bokförda produktinleveranser på fakturarader som en tresiffrig matchningsprincip definieras för. Processen kommer att köras tills den matchade kvantiteten för produktinleverans är lika med fakturaantalet, eller tills värdet av fältet **antal gånger som ett nytt matchande** har nåtts. Processen kan köras tills fakturan har skickats till arbetsflödessystemet.

    Det här alternativet är endast tillgängligt om alternativet **Aktivera fakturamatchningsvalidering** har valts.

    Om du ställer in **matcha produktinleveranser mot fakturarader innan alternativet för automatisk matchning** till **Ja**, kan det här alternativet inte ställas in på **Nej**. Om du ställer in det här alternativet på **Nej** måste du först ange alternativet **matcha produktinleveranser mot fakturarader innan alternativet för automatisk matchning** till **Nej**.

- **Antal gånger för att försöka med automatisk matchning** – Välj det antal gånger som systemet ska försöka matcha produktinleveranser mot en fakturarad innan det finner att processen misslyckades. När det angivna antalet försök har nåtts tas fakturan bort från automatiseringsbearbetningen.

