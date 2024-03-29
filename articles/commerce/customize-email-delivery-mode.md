---
title: Anpassa transaktionsmeddelanden per e-post efter leveranssätt
description: I denna artikel beskrivs hur du konfigurerar anpassade e-postmallar för specifika meddelandetyper och leveranssätt i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 0c0bd218c10a373d142ddcc7780c5339569f7a07
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275715"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a>Anpassa transaktionsmeddelanden per e-post efter leveranssätt

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar anpassade e-postmallar för specifika meddelandetyper och leveranssätt i Microsoft Dynamics 365 Commerce.

Transaktionsmeddelanden via e-post kan nu anpassas för en kombination av en meddelandetyp (t. ex. **Order skapad**, **Order förpackad** eller **Order fakturerad**) och ett leveranssätt (t. ex. nästa dag, upphämtning i butik eller drive in-upphämtning). Anpassade transaktionsmeddelanden via e-post gör att återförsäljare tillhandahåller kundorder med uppfyllelseupplevelser som är skräddarsydda efter orderns leveranssätt. Händelsen "order packad" kan till exempel anpassas så att den tillhandahåller instruktioner rörande drive in-upphämtning till för kunder som väljer detta alternativ. Det kan också tillhandahålla information om speditör och leverans för kunder som väljer att låta ordern levereras.

> [!NOTE]
> Om du vill använda funktionen för anpassade transaktionsmeddelanden via e-post måste du först aktivera funktionen **Anpassa transaktionsmeddelanden via e-post efter leveranssätt** genom att gå till **Arbetsytor \> Funktionshantering** i Commerce headquarters.

E-postmeddelanden kan anpassas efter leveranssätt för följande meddelandetyper:

- **Annullering av order** – Denna meddelandetyp via e-post är ny.
- **Order skapad**
- **Ordern är bekräftad**
- **Order fakturerad** – Denna meddelandetyp via e-post är ny. Den kan användas istället för meddelandetypen **Order skickad** som skickar ett meddelande för alla fakturahändelser med som har ett leveranssätt som innefattar avsändande (ej upphämtning, utkörning eller elektroniskt leveranssätt).
- **Order plockad**
- **Order packad**
- **Order klar för upphämtning** – Denna meddelandetyp kan bara anpassas efter leveranssätt om funktionen **Stöd för flera leveranssätt genom upphämtning** har aktiverats. I så fall är denna meddelandetyp funktionellt likvärdig med meddelandetypen **Order packad**.
- **Betalning lyckades inte**
- **Ersättningsorder skapad**

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a>Konfigurera e-postmallar för specifika leveranssätt

För denna procedur görs antagandet att du redan har skapat dina nya, anpassade e-postmallar och lagt till dessa på sidan **E-postmallar för organisation**. Information om hur du skapar och överför e-postmallar finns i [Skapa e-postmallar för transaktionshändelser](email-templates-transactions.md).

Följ dessa steg om du vill konfigurera e-postmallar för specifika leveranssätt i Commerce headquarters.

1. Gå till **Meddelandeprofil via e-post i Commerce**.
1. Under **Meddelandeinställningar för butikshändelse** väljer du en befintlig meddelandetyp.
1. När meddelandetypen fortfarande är markerad väljer du **Konfigurera leveranssätt**.
1. I dialogrutan **Leveranssätt** väljer du **Nytt**.
1. I den nya raden i fältet **Leveranssätt** väljer du ett leveranssätt.
1. I fältet **ID- för e-post** väljer du den e-postmall du vill mappa till leveranssättet.
1. Markera kryssrutan **Aktiv**.
1. Upprepa steg 4 till 7 om du vill lägga till fler leveranssätt.
1. Välj **OK** när du är klar.

> [!NOTE]
> - När det finns fler än ett leveranssätt över flera rader i en försäljningsorder används standardmallen. Standardmallen är den mall som mappas till meddelande typen på sidan **Meddelandeprofil via e-post för Commerce**.
> - Om en försäljningsorder har ett leveranssätt som inte har konfigurerats för en anpassad e-postmall, kommer standard-e-postmallen att användas.

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa kundtjänstorder](tasks/create-call-center-orders.md)

[Ändra leveranssätt i POS](pos-change-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
