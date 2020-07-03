---
title: Skapa och tillämpa villkor för innehållen leverantörsbetalning
description: I det här avsnittet finns information om hur du ställer in och underhåller villkor för kvarhållande för leverantörsbetalningar.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410269"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a>Skapa och tillämpa villkor för innehållen leverantörsbetalning

[!include [banner](../includes/banner.md)] 

Att ställa in kvarhållande av leverantörsbetalningsvillkor för ett projekt är användbart när organisationen vill behålla en del av betalningarna som har gjorts till en leverantör. Till exempel när du vill spärra betalning till en leverantör tills de produkter som levererats uppfyller dina förväntningar. Villkor för leverantörsbetalning kan anges när du förhandlar om ett leverantörskontrakt.

## <a name="create-vendor-payment-retention-terms"></a>Skapa kvarhållandevillkor för leverantörsbetalning

Du kan ange procentandelen av en leverantörsbetalning för kvarhållande som du vill hålla inne och procentandelen av tidigare innehållna belopp som ska frisläppas. Belopp hålls automatiskt inne på leverantörsfakturor tills avtalet når den angivna slutförandefasen. När du har ställt in kvarhållandevillkoren kan du tillämpa dem på alla projekt för den leverantören.

Använd följande steg om du vill ställa in och underhålla villkor för innehållet belopp i leverantörsbetalningar. 

1. Gå till **Projekthantering och redovisning** > **Kvarhållande** > **Villkor för innehållen leverantörsbetalning**.
2. Välj **Nytt** om du vill lägga till ett nytt villkor för innehållet belopp. Värdet i **Regel-ID** för det nya villkoret anges i automatiskt. 
3. Ange en kort beskrivning i fältet **Beskrivning** och snabbfliken **Villkor**, välj **Lägg till rad** om du vill ange villkorsvärden för följande:

   - **Levererade enheter i procent**: Ange en slutförandeprocent för villkoret. Belopp hålls inne automatiskt på leverantörsfakturor tills projektslutförandefasen är lika med procentsatsen som du anger. Om du till exempel anger 50,00 hålls beloppen inne tills projektet är 50 procent slutfört.
   - **Procent att hålla inne**: Ange en procentandel av leverantörsfakturor som ska hållas inne. Om du till exempel anger 10,00 hålls 10 procent av beloppet på leverantörsfakturorna inne tills projektet når slutförandeprocenten som du väljer i formuläret **Levererade enheter i procent**.
   - **Procent att frisläppa**: Välj **Lägg till rad** för att ange en procentandel av tidigare behållna belopp som ska frisläppas för den valda nivån för projektets slutförande.

> [!NOTE]
> Om du har mer än en milstolpe för olika nivåer för projektslutförande anger du en separat rad för villkor för innehållet belopp för varje regel. Varje rad kan ange en annan kvarhållandeprocentsats och en annan procentsats för frisläppning på varje nivå av projektslutförande.

När du har skapat villkor för återförsäljare för en leverantör kan du tillämpa villkoren på ett projekt.

## <a name="apply-vendor-retention-terms-to-a-project"></a>Tillämpa innehållet belopp till leverantören på ett projekt

1. Gå till **Projekthantering och redovisning** > **Projekt** > **Alla projekt** och öppna ett projekt från sidan projektlista.
2. Klicka på **Lägg till rad** på snabbfliken, välj **Leverantörsavtal**.
3. Välj ett av följande alternativ i fältet **Kontokod**: 

   - **Tabell**: Villkoren för innehållet belopp till leverantören gäller för en enskild leverantör.
   - **Grupp**: Villkor för innehållet belopp till leverantören gäller för alla leverantörer inom en leverantörsgrupp.
   - **Alla**: Villkor för innehållet belopp till leverantören gäller för alla leverantörer.

4. Välj den leverantör eller leverantörsgrupp som villkoren för innehållet belopp gäller för i fältet **Leverantör/leverantörsgrupp**. Om du har valt **Alla** i det föregående steget är det här fältet inte tillgängligt.
5. I fältet **Villkor för kvarhållande** väljer du de kvarhållandevillkor som du skapade i föregående procedur.
6. Om projektet även har bet. vid bet.-villkor inställda för leverantören använder du fältet **Bet. vid bet.-tröskelprocent** och anger ingångsprocentsatsen för projektet.

Villkoren för innehållet belopp till leverantören visas också på inköpsorder som du skapar för leverantören.
