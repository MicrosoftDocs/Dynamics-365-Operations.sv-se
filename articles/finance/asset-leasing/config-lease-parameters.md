---
title: Konfigurera leasingparametrar (förhandsversion)
description: I det här ämnet beskrivs konfigurationsinställningarna för Leasing av tillgångar , t.ex. säkerhetsinformation och redovisningsinställningar.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2a644b3c9d9ed4fc86a816af1ab338b96b1aa7ad
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968087"
---
# <a name="configure-lease-parameters"></a>Konfigurera leasingparametrar

[!include [banner](../includes/banner.md)]

Flera konfigurationsinställningar påverkar hur Leasing av tillgångar uppträder. Dessa inställningar omfattar journalnamn, allmänna parametrar och inställningar för bokföringsprofiler.

1. Gå till **Leasing av tillgångar \> Konfigurera \> Parametrar för tillgångsleasing**.
2. Välj fliken **Allmänt** på fliken **Leasing**.

    Parametern **Tillåt manuell åsidosättning av klassificering** avgör om leasingklassificeringen kan åsidosättas innan betalningsplanen bekräftas.

    Parametern **Korsentitetsbatch** avgör om du kan bokföra till andra juridiska personer från den aktuella juridiska personen. Om den här parametern är aktiverad kan du skapa journalposter för de juridiska personer som du har åtkomst till.

3. Ställ in alternativet **Tillåt borttagning av bekräftad leasing** till **Ja** om du vill tillåta att leasingar som har bekräftade betalningsplaner raderas. Leasingar kan inte tas bort om bokförda eller ej bokförda transaktioner är kopplade till dem, oavsett inställningen för detta alternativ. Du kan inte återställa en leasingpost när den har tagits bort. Om du laddar upp poster för ett borttaget lån, antingen manuellt eller via dataentiteter, behandlas den uppladdade informationen som ny, inte som en uppdatering av en befintlig leasing.

    Om du ställer in det här alternativet på **Ja**, och övergångstypen för boken är **Kumulativt catchup-alternativ A eller B**, ställer systemet in fältet **Marginell låneränta** till värdet i fältet **Marginell låneränta vid övergång** på sidan **Bokinställning**. Om detta alternativ är inställt på **Nej**, ställs satsen i leasinghuvudet in på värdet för fältet **Marginell låneränta** på sidan **Information om bok**, oavsett övergångstypen för boken.

4. Ställ in alternativet **Tillåt återföringar av avskrivningar på stängd bok** till **Ja** för att göra så att avskrivningsutgiftstransaktioner kan återföras. Utgiftstransaktioner kan återföras även om bokversionen är stängd.

    > [!NOTE]
    > Vi rekommenderar att du behåller detta alternativ angivet till **Nej**. Inställningen för det här alternativet används som en validering och kontroll för att förhindra att en stängd boks version avskrivs av misstag. Genom att välja **Nej** kan du hålla det bokförda nettovärdet och framtida avskrivningsberäkningar korrekta.

5. Ställ in alternativet **Tillåt uppdelning av betalningsbelopp** till **Ja** för att tillåta en uppdelning av betalningsbeloppen på **Betalningsplanrader** på **Leasing**. Typerna för betalningsuppdelning definieras under **Inställningar** på sidan **Betalningsbeloppstyper**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
