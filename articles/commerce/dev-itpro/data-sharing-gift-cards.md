---
title: Datadelning för presentkort mellan företag
description: I den här artikeln beskrivs hur du konfigurerar Microsoft Dynamics 365 Commerce till att använda Dynamics 365 Finance funktioner för datadelning mellan dataområden för att synkronisera presentkortsdata.
author: BrianShook
ms.date: 08/26/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: b56890b546c3cd74b75cf447e62495733ea8d288
ms.sourcegitcommit: 09d4805aea6d148de47c8ca38d8244bbce9786ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387075"
---
# <a name="cross-company-data-sharing-for-gift-cards"></a>Datadelning för presentkort mellan företag

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

I den här artikeln beskrivs hur du konfigurerar Microsoft Dynamics 365 Commerce till att använda Dynamics 365 Finance funktioner för datadelning för att synkronisera presentkortsdata. Datapostdelningsfunktionen kan sedan användas för att dela data mellan företag mellan två dataområden. På detta sätt kan den interna presentregisteren för Commerce dela data mellan två företagsenheter. Mer information om datadelning mellan företag i Dynamics 365 Finance finns i [datadelning mellan företag](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

## <a name="key-terms"></a>Nyckeltermer

| Villkor | Beskrivning |
|---|---|
| Företag | Den juridiska personen i Dynamics 365 Finance-miljön. |
| Presentkort | Den Dynamics 365 Commerce interna presentkortsprodukten. |

## <a name="prerequisites"></a>Förutsättningar

Användarna måste konfigurera sin miljö för datadelning mellan företag på det sätt som beskrivs i [datadelning mellan företag](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

**RetailGiftCardTable** måste ha fältet **DataSharingType** inställt på **Duplicate** för att aktivera dubbletter av postdelning (DRS) för presentkortsregistret. Mer information finns i [Datadelning mellan företag för utvecklare](/dynamics365/fin-ops-core/dev-itpro/sysadmin/drs-srs-dev).

## <a name="configure-cross-company-data-sharing-for-gift-cards"></a>Konfigurera datadelning för presentkort mellan företag

Konfigurera datadelning för presentkort mellan företag genom att följa dessa steg.

1. I Commerce headquarters, gå till **Systemadministration \> Inställningar \> Konfigurera datadelning mellan företag**.
1. I åtgärdsfönstret, välj **Ny** för att lägga till en post för datadelning.
1. I fältet **Namn** ange ett namn för datadelningsposten (till exempel, **Presentkort**).
1. I avsnittet **Register och fält att dela**, välj **Lägg till**.
1. I dialogrutan **Dela ny register** i fältet **Registernamn** ange **RETAILGIFTCARDTABLE** (registeren för presentkort i butik). Fältet **Registeretikett** ska automatiskt ställas in på **Presentkortsregister**.
1. Kontrollera att alla kryssrutor **Spara data per företag**, **Har unikt index** och **Inte delat än** är markerade. Om du markerar dessa kryssrutor initieras valideringar som hör till datadelningsfunktionen.
1. Välj **Lägg till registrer**. Posten **Presentkortsregister (RetailGiftCardTable)** bör nu visas under **Register och fält som ska delas**. Välj symbolen för caret (^) om du vill visa alla registerfält som automatiskt associeras med registret för delning.
1. I avsnittet **Företag som delar uppgifterna i dessa register**, välj **Lägg till** för att lägga till företag som du vill dela data med.
1. I raden under **företag**, välj ett företag i listrutan.
1. I fältet **Namn**, ange företagsnamnet.
1. Upprepa steg 8 till och med 10 om du vill lägga till fler företagsrader.
1. När du har lagt till alla företagsrader markerar du **Aktivera** i åtgärdsfönstret.
1. Du får ett varningsmeddelande där det står: Det rekommenderas att du endast utför den här åtgärden under tider utanför företaget. Det går inte att köra samtidiga transaktionsåtgärder för register i policyn. Vill du fortsätta? Klicka på **Ja** för att godkänna.
1. Du får ett varningsmeddelande som anger: Vill du kopiera alla befintliga data i alla delade företag nu? Klicka på **Ja** för att godkänna.

När du har enas om båda meddelandena börjar registren kopiera data inom de konfigurerade företagen. Saldon som inträffar mot ett företags presentkort visas sedan för det andra företaget.

## <a name="additional-resources"></a>Ytterligare resurser

[Vanliga frågor om betalningar](payments-retail.md)

[Kassamodul](../add-checkout-module.md)

[Betalningsmodul](../payment-module.md)
