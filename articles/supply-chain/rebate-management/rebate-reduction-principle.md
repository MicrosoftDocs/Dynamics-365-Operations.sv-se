---
title: Principer för rabattreducering
description: I det här avsnittet beskrivs hur du ställer in principer för reducering. Principer för reducering styr beteendet när flera rabatter gäller för samma artikel eller transaktion.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: fec7f94aba46f8b1853e0520169dd628fd940a56
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8685951"
---
# <a name="rebate-reduction-principles"></a>Principer för rabattreducering

[!include [banner](../includes/banner.md)]

Du kan gruppera rabatthanteringserbjudanden *principer för reducering* för att minska andra provisioner som är associerade med en artikel och/eller för att minska de resulterande värdena för rabattberäkningar. När principerna för rabattreducering har ställts in kan du eventuellt tilldela dem till raderna i dina rabatthanteringserbjudanden.

Principer för rabattreducering gäller bara om rabatterbjudanden överlappar varandra. Därför kan de bevilja flera rabatter i situationer där flera rabatter inte finns.

## <a name="manage-rebate-reduction-principles"></a>Hantera principer för rabattreducering

Om du vill arbeta med principer för rabattreducering går du till **Rabatthantering \> Inställningar \> Principer för rabattreducering**. Med knapparna i åtgärdsfönstret kan du lägga till och ta bort principer för reducering efter behov. På varje princip anger du fälten enligt beskrivningen i följande tabell.

| Fält | beskrivning |
|---|---|
| Princip för rabattreducering | Ange ett unikt namn för rabattreduceringsprincipen. |
| beskrivning | Ange en beskrivning för rabattreduceringsprincipen. |
| Använd reducering | Markera den här kryssrutan om du vill använda ett reduceringsunderlag för rabatter som tillhör den här rabattreduceringsprincipen. |
| Reduceringsunderlag | Om du har markerat kryssrutan **Använd reducering** väljer du reduceringsunderlag (*Provision*, *Rabatter* eller *Båda*). Om du väljer *Både* och om både en reservering och en rabatt har bokförts för ett tidigare erbjudande, tillämpas endast rabatten. |
| Exkludera från reducering | Om den här kryssrutan markeras exkluderas provisioner och rabatter som tillhör den här rabattreduceringsprincipen från efterföljande reduceringar. Inställningen i fältet **Reduceringsunderlag** gäller inte för den här inställningen. |

## <a name="examples-of-rebate-reduction-principle-setups"></a>Exempel på inställningar för rabattreduceringsprinciper

Följande tabell innehåller några typiska exempel på inställningar för rabattreduceringsprinciper. För var och en av dessa rabatter minskar principerna **Beskrivning** beskriver syftet med rabattreduceringsprincipen.

| Princip för rabattreducering | beskrivning | Använd reducering | Reduceringsunderlag | Exkludera från reducering |
|---|---|---|---|---|
| Uppskjutet | Minska rabatten | Ja | Båda | Nej |
| Exclreb | Exkludera rabatt | Ja | Rabatt | Ja |
| Flera | Flera rabatter | Ja | Båda | Ja |
| None | Endast prov och rabatt | Nej | Båda | Ja |
| Reservera | Endast provision | Ja | Reservera | Nej |
| Rabatt | Endast rabatt | Ja | Rabatt | Ja |

## <a name="examples-of-rebate-reduction-principle-calculations"></a>Exempel på inställningar för rabattreduceringsberäkningar

Du har en försäljningsorder som har en enskild försäljningsorderrad. Den här raden har ett värde 1 000 USB. Följande erbjudanden gäller för beställningen:

- **Erbjudande 1:** 10 procent på 1 000 USD
- **Erbjudande 2:** 15 procent på 1 000 USD
- **Erbjudande 3:** 20 procent på 1 000 USD
- **Erbjudande 4:** 25 procent på 1 000 USD

Bearbetningsordningen är mycket viktig. Bearbetningsordningen baseras på hur du arbetar, på det sätt som beskrivs i [Bearbeta, granska och bokföra rabatter](process-review-post.md).

Följande tabell sammanfattar till exempel resultatet om du använder order *1, 2, 3, 4* och om du bara bearbetar provisioner.

| Överenskommelse | Beskrivning och inställningar | Provisionsresultat |
|---|---|---|
| 1 | <p>Klassificeringen kontrollerar inte andra erbjudanden för reduceringar. Kontrollen görs både för provisioner och rabatter.</p><ul><li>**Använd reducering:** *Nej*</li><li>**Reduceringsunderlag:** *Båda*</li><li>**Exkludera från reducering:** *Nej*</li></ul> | 1 000 × 10 % = 100 USD |
| 2 | <p>Klassificeringen kontrollerar andra avtal för reduceringar, men flaggas så att den ignoreras. Kontrollen utförs endast för rabatter.</p><ul><li>**Använd reducering:** *Ja*</li><li>**Reduceringsunderlag:** *Rabatt*</li><li>**Exkludera från reducering:** *Ja*</li></ul> | 1 000 × 15 % = 150 USD |
| 3 | <p>Klassificeringen kontrollerar andra erbjudanden för reduceringar. Kontrollen görs både för provisioner och rabatter.</p><ul><li>**Använd reducering:** *Ja*</li><li>**Reduceringsunderlag:** *Båda*</li><li>**Exkludera från reducering:** *Nej*</li></ul> | (1 000 USD – erbjudande 1) × 20 % = 180 USD |
| 4 | <p>Klassificeringen kontrollerar andra erbjudanden för reduceringar. Kontrollen görs både för provisioner och rabatter.</p><ul><li>**Använd reducering:** *Ja*</li><li>**Reduceringsunderlag:** *Båda*</li><li>**Exkludera från reducering:** *Nej*</li></ul> | ( 1 000 USD – erbjudande 1 – erbjudande 3) × 25 % = 180 USD |

Följande tabell innehåller några exempel där provision bearbetas i olika order och där olika totalsummor därför uppnås. Avvikelsen i bestämmelserna beror på i vilken ordning som systemet bearbetar erbjudanden. Det är viktigt att du förstår hur bearbetningsordningen påverkar det slutliga rabattbeloppet.

| Sekvens | Beräkning |
|---|---|
| 1<br>(1, 2, 3, 4) | <ul><li>**Erbjudande 1:** 1 000 USD × 10 % = 100 USD</li><li>**Erbjudande 2:** 1 000 USD × 15 % = 150 USD</li><li>**Erbjudande 3:** (1 000 USD – Erbjudande 1) × 20 % = 180 USD</li><li>**Erbjudande 4:** (1 000 USD – Erbjudande 1 – Erbjudande 2) × 25 % = 180 USD</li><li>**Summa provision:** 610 USD</li></ul> |
| 2<br>(4, 3, 2, 1) | <ul><li>**Erbjudande 4:** 1 000 USD x 25 % = 250 USD</li><li>**Erbjudande 3:** (1 000 USD – Erbjudande 4) × 20 % = 150 USD</li><li>**Erbjudande 2:** 1 000 USD x 15 % = 150 USD</li><li>**Erbjudande 1:** 1 000 USD x 10 % = 100 USD</li><li>**Summa provision:** 650 USD</li></ul> |
| 3<br>(3, 2, 1, 4) | <ul><li>**Erbjudande 3:** 1 000 USD x 20 % = 200 USD</li><li>**Erbjudande 2:** 1 000 USD x 15 % = 150 USD</li><li>**Erbjudande 1:** 1 000 USD x 10 % = 100 USD</li><li>**Erbjudande 4:** (1 000 USD – Erbjudande 3 – Erbjudande 1) × 25 % = 175 USD</li><li>**Summa provision:** 625 USD</li></ul> |
| 4<br>(2, 4, 1, 3) | <ul><li>**Erbjudande 2:** 1 000 USD × 15 % = 150 USD</li><li>**Erbjudande 4:** 1 000 USD × 25 % = 250 USD</li><li>**Erbjudande 1:** 1 000 USD × 10 % = 100 USD</li><li>**Erbjudande 3:** (1 000 USD – Erbjudande 4 – Erbjudande 1) × 20 % = 130 USD</li><li>**Summa provision:** 630 USD</li></ul> |
