---
title: Bearbeta icke-kopplade återrbetalningar med Dynamics 365 Commerce-betalningsanslutningen för Adyen
description: I denna artikel beskrivs hur icke-kopplade återbetalningar fungerar när Microsoft Dynamics 365-betalningsanslutningen för Adyen används.
author: BrianShook
ms.date: 10/07/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: BrShoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 634b30de7adbfb0c316fe14456581ea8eb89d070
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885207"
---
# <a name="process-unlinked-refunds-with-the-dynamics-365-commerce-payment-connector-for-adyen"></a>Bearbeta icke-kopplade återrbetalningar med Dynamics 365 Commerce-betalningsanslutningen för Adyen

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur icke-kopplade återbetalningar fungerar när [Microsoft Dynamics 365-betalningsanslutningen för Adyen](adyen-connector.md) används. Här granskas också möjligheten att bearbeta en återbetalning mot en ny betalningsmetod i kassa eller kundtjänst.

Dynamics 365-betalningsanslutningen för Adyen ger stöd åt möjligheten att bearbeta återbetalningar med hjälp av en annan betalningsmetod än den som användes för den ursprungliga transaktionen. Även om vi rekommenderar att du använder [kopplade återbetalningar](linked-refunds.md) för att bearbeta en återbetalning mot den betalningsmetod som ursprungligen tillhandahölls, krävs i vissa fall återbetalnming till en annan metod. Till exempel kan kortet som användes för den ursprungliga betalningen nu ha förfallit eller förlorats, eller också kan det ha annullerats av användaren.

## <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste uppfyllas innan Dynamics 365-betalningsanslutningen för Adyen kan bearbeta icke-kopplade återbetalningar:

- Ange [betalningsmetoder](../payment-methods.md).
- Konfigurera [betalningar via flera olika kanaler](../omni-channel-payments.md).

## <a name="additional-configuration"></a>Ytterligare konfiguration

Dynamics 365-betalningsanslutningen för Adyen innehåller en färdig implementering för samtliga återbetalningsscenarier som beskrivs i nästa avsnitt. Kunder som inte använder den färdiga implementeringen av Dynamics 365-betalningsanslutningen för Adyen måste konfigurera det anslutningsprogram som stöder omvandling av kreditkort till token.

## <a name="supported-refund-scenarios"></a>Stödda ẗerbetalningsscenarier

Dynamics 365 Commerce stöder återbetalning av transaktioner som tidigare godkänts och bekräftats. En återbetalning kan bestå av antingen en fullständig återbetalning eller en delåterbetalning av transaktionen. Återbetalningar får inte överstiga hela beloppet i den ursprungliga betalningsauktoriseringen. Icke-kopplade återbetalningar stöds bara i kassa och kundtjänst.

## <a name="enable-unlinked-refunds-functionality"></a>Aktivera funktionen för icke-kopplad återbetalningar

För att aktivera funktionen för icke-kopplade återbetalningar i Commerce headquarters, följ dessa steg.

1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> delade Commerce-parametrar**.
1. På fliken **Betalningar i flera kanaler** anger du alternativet **Använd betalningar i flera kanaler** som **Ja**.

### <a name="supported-payment-method-variants"></a>Varianter av betalningsmetod som stöds

Följande betalningsmetodvarianter stöder icke-kopplade återbetalningar direkt:

- Kort
- Plånbok

Alla betalningsmetodvarianter har inte stöd för icke-kopplade återbetalningar. Följande tabell anger en lista över vanliga betalningsmetoder samt visar varje metods stödkapacitet för kopplade och icke-kopplade återbetalningar.

| Betalningsmetod        | Länkad återbetalning | Icke-kopplad återbetalning |
|-----------------------|:-------------:|:---------------:|
| amexcommercial        | Ja           | Ja             |
| amexconsumer          | Ja           | Ja             |
| amexcorporate         | Ja           | Ja             |
| amexdebit             | Ja           | Ja             |
| amexförskottsbetalning           | Ja           | Ja             |
| amexprepaidreloadable | Ja           | Ja             |
| amexsmallbusiness     | Ja           | Ja             |
| discover              | Ja           | Ja             |
| maestro               | Ja           | Ja             |
| maestrouk             | Ja           | Ja             |
| mc                    | Ja           | Ja             |
| mcalphabankbonus      | Ja           | Ja             |
| mcprepaidanonymous    | Ja           | Ja             |
| visa                  | Ja           | Ja             |
| visaalphabankbonus    | Ja           | Ja             |
| visacheckout          | Ja           | Ja             |
| visadankort           | Ja           | Ja             |
| visahipotecario       | Ja           | Ja             |
| visasaraivacard       | Ja           | Ja             |
| vpay                  | Ja           | Ja             |
| givex                 | **Nej**        | Ja             |
| svs                   | **Nej**        | Ja             |
| kopp                   | Ja           | Ja             |
| diners                | Ja           | Ja             |
| interac               | **Nej**        | Ja             |
| jcb                   | Ja           | Ja             |
| jcb_applepay          | Ja           | Ja             |
| unionpay              | Ja           | Ja             |

### <a name="process-an-unlinked-refund-in-pos"></a>Bearbeta en icke-kopplad återbetalning i kassan

En kund returnerar en artikel till en kassör inom den tillåtna perioden för returer och har en giltig inleverans. Under bearbetningen av returen innehåller dialogrutan **Returbetalning** alternativet **Välj en betalningsmetod**. Kassören kan sedan välja en betalningsmetod bland de betalningsmetoder som stöds återbetalningar (kort och kontanter).

### <a name="process-an-unlinked-refund-in-call-center"></a>Bearbeta en icke-kopplad återbetalning i kundtjänst

När en icke-kopplad återbetalning bearbetas mot en order i kundtjänst, väljer en kundtjänstanställd en betalningsmetod som skiljer sig från den ursprungliga metoden. Medarbetaren uppmanas sedan att skaffa en ett personligt ID-nummer för administratörsåsidosättande (PIN). PIN-koden måste anges innan den andra betalningsmetoden kan bearbetas för återbetalningen.

#### <a name="set-up-an-administrator-override-pin-for-call-center"></a>Konfigurera en PIN-kod för administratörsåsidosättande för kundtjänst

Följ dessa steg för att konfigurera en PIN-kod för administratörsåsidosättande för kundtjänst i Commerce headquarters.

1. Gå till **Retail och Commerce \> Kanalkonfiguration \> Konfiguration av kundtjänst** eller sök efter "Åsidosättning av behörigheter".
1. Välj den roll för vilken du vill tillåta behörigheter för icke-kopplad återbetalning.
1. På snabbfliken **Returer** anger du alternativet **Tillåt alternativ betalning** som **Ja**.

## <a name="additional-resources"></a>Ytterligare resurser

[Dynamics 365 Payment Connector för Adyen](adyen-connector.md)

[Kopplade återbetalningar av tidigare godkända och bekräftade transaktioner](linked-refunds.md)
