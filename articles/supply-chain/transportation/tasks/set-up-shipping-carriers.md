---
title: Konfigurera transportföretag
description: I denna artikel beskrivs hur du konfigurerar ett transportföretag och definierar detaljer såsom tjänster, leveranssätt, transportanbud, transportbegränsningar och leveranskostnader.
author: Weijiesa
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSShippingCarrierCustomerAccount,TMSCarrier
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 48586a0ddaa7cd95a81380dadffef8f276076dd2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858984"
---
# <a name="set-up-shipping-carriers"></a>Konfigurera transportföretag

[!include [banner](../../includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar ett transportföretag och definierar detaljer såsom tjänster, leveranssätt, transportanbud, transportbegränsningar och leveranskostnader. En transportkoordinator kan sedan tilldela ett transportföretag till en inkommande eller utgående beläggning.

## <a name="create-a-new-shipping-carrier"></a>Skapa ett nytt transportföretag

1. Gå till **Navigeringsfönster > Moduler >Transporthantering > Inställningar > Transportföretag > Transportföretag**.
2. Välj **Ny** i åtgärdsfönstret.
3. Skriv ett värde i fältet **Transportföretag**.
4. Skriv ett värde i fältet **Namn**.
5. I fältet **Metod** väljer du ett alternativ i den nedrullningsbara menyn.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>Fyll i den allmänna informationen för transportföretaget

1. Växla expanderingen av avsnittet **Översikt**.
2. Markera eller avmarkera kryssrutan **Aktivera transportföretag**.
3. I fältet **Leverantörskonto** väljer du ett alternativ i den nedrullningsbara menyn. Välj det leverantörskonto som du vill tilldela transportföretaget till.  
4. Välj ett alternativ i fältet **Typ av transportanbud**. Välj **Manuell** för att använda sidan Transportanbud eller välj **EDI** för att uppdatera anbudet med hjälp av EDI (Electronic Data Interchange).  
5. Markera eller avmarkera kryssrutan **Aktivera värdering av transportföretag**.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>Skapa nödvändiga tjänster för det transportföretaget

1. Växla expanderingen av avsnittet **Tjänster**.
2. Välj **Ny**.
3. Skriv ett värde i fältet **Transportföretagstjänst**.
4. Skriv ett värde i fältet **Namn**.
5. I fälten **Lastmall-ID** välj en laddningsmall att associera med tjänsten. Beläggningsmallen definierar maximala mått för vikt och volym för hela beläggningen. Beläggningsmallen kan till exempel representera storleken på en behållare eller en lastbil. Lastmalls-ID anges också i lastbyggnadsmallar och när du använder [lastuppbyggnadsworkbench](load-building-workbench.md), som hjälper dig att tillämpa lastbyggande strategier för att skapa laster. Följden blir att systemet kan matcha varje ny beläggning mot en lämplig transportföretagstjänst genom att jämföra de angivna beläggningsmall-ID:erna.
6. I fältet **Transportmetod** väljer du ett alternativ i den nedrullningsbara menyn.

## <a name="set-up-the-address-for-the-carrier-optional"></a>Ställ in för adress för transportföretaget (valfritt)

1. Växla utökningen av avsnittet **Adresser** .
2. Välj **Ny**.
3. Skriv ett värde i fältet **Namn eller beskrivning**.
4. I fältet **Land/region** väljer du ett alternativ i den nedrullningsbara menyn.
5. I fältet **Postnummer** väljer du ett alternativ i den nedrullningsbara menyn.
6. Ange ett värde i fältet **Gata**.
7. Välj **OK**.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>Ställa in bedömningsprofil för transportföretaget

1. Växla expanderingen av avsnittet **Bedömningsprofiler**.
2. Välj **Ny**.
3. Skriv ett värde i fältet **Bedömningsprofil**.
4. Skriv ett värde i fältet **Namn**.
5. I fältet **Plats** väljer du ett alternativ i den nedrullningsbara menyn.
6. I fältet **Lagerställe** väljer du ett alternativ i den nedrullningsbara menyn.
7. I fältet **Tariffmotor** väljer du ett alternativ i den nedrullningsbara menyn. Välj den tariffmotor som överensstämmer med det kontrakt som du har för transportföretaget.  
8. I fältet **Tariffmall** väljer du ett alternativ i den nedrullningsbara menyn.
9. I fältet **Transporttidsmotor** väljer du ett alternativ i den nedrullningsbara menyn.
10. Välj **Spara**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]