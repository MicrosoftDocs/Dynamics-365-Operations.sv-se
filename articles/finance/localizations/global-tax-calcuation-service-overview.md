---
title: Skatteberäkning (förhandsversion)
description: Detta ämne innehåller information om skatteberäkningsfunktionens övergripande omfattning och funktioner.
author: wangchen
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3df952e0632807e55f176e63dc2047be5e622ec2
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892359"
---
# <a name="tax-calculation-preview"></a>Skatteberäkning (förhandsversion)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Skatteberäkningen är en hyperskalbar tjänst för flera innehavare som gör det möjligt för den globala skattemotorn (Global Tax Engine) att automatisera och förenkla bestämmandet och beräkningsprocessen för skatt. Skattemotorn är helt konfigurerbar. Elementen som kan konfigureras är inklusive, men inte begränsat till, den beskattningsbara datamodellen, skattekoden, tillämplighetsmatrisen för skatt och beräkningsformeln för skatt. Skattemotorn körs på Microsoft Azure kärntjänsters plattform och erbjuder modern teknik och exponentiell skalbarhet.

Beräkningstjänsten för skatt går att integrera med Dynamics 365 Finance och Dynamics 365 Supply Chain Management. Så småningom kommer den också att integreras Dynamics 365 Project Operations, Dynamics 365 Commerce och andra applikationer från första och tredje part.

Skatteberäkningstjänsten är en mikrotjänstbaserad skattemotor som erbjuder exponentiell skalbarhet. Det kan hjälpa dig att utföra följande uppgifter:

- Konfigurera beräkningstjänsten för skatt via Regulatory Configuration Service (RCS). RCS är en förbättrad version av designern Elektronisk rapportering (ER) och är tillgänglig som en fristående tjänst.
- Konfigurera skattematrisen om du automatiskt vill bestämma skattekoder och skattesatser.
- Konfigurera skattematrisen om du automatiskt vill bestämma skatteregistreringsnummer.
- Konfigurera designern för skatteberäkning om du vill definiera formler och villkor.
- Dela lösningen för skattebestämning och beräkning mellan juridiska personer.

Om du vill använda beräkningstjänsten för skatte ska du installera tillägget för skatteberäkningstjänsten från projektet i Microsoft Dynamics Lifecycle Services (LCS). Slutför sedan inställningarna i RCS och aktivera skatteberäkningstjänsten i Finance och Supply Chain Management. För mer information, se [Kom igång med skattetjänsten](./global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Tillgänglighet

Skatteberäkningstjänsten är bara tillgänglig i sandbox-miljöer och för utvalda kunder, detta via en allmänt tillgänglig förhandsversion. Så småningom blir den allmänt tillgänglig för alla kunder och i produktionsmiljöer.

Nya funktioner kommer att tillkomma - kontrollera därför den senaste dokumentationen ofta för att ta reda på omfattningen av de funktioner som stöds.

Skatteberäkningstjänsten distribueras på följande Azure-områden: Den kommer även att distribueras till fler Azure-geologer, baserat på kundernas behov:

- USA
- Europa

> [!NOTE]
> Skatteberäkningstjänsten har inte stöd för lokala distributioner av Dynamics 365. Den stöder inte heller tidigare versioner, till exempel Dynamics AX 2012.

## <a name="feature-highlights"></a>Funktionens höjdpunkter

- Konfigurera skattematrisen om du automatiskt vill bestämma och beräkna skatt
- Stöd för flera skatteregistreringsnummer
- Överföringsorderstöd för bestämning och beräkning av skatter
- Stöd för överföringsorder med syfte att bestämma flera skatteregistreringsnummer

## <a name="supported-transactions"></a>Transaktioner som stöds

Skatteberäkningstjänsten kan aktiveras av juridisk person och transaktion. Följande transaktioner stöds:

- Försäljningsprocess

    - Försäljningsoffert
    - Försäljningsorder
    - Bekräftelse
    - Plocklista
    - Följesedel
    - Försäljningsfaktura
    - Kreditfaktura
    - Returorder
    - Övriga avgifter för rubrik
    - Övriga avgifter för rad

- Inköpsprocess

    - Inköpsorder
    - Bekräftelse
    - Inleveranslista
    - Produktinleverans
    - Inköpsfaktura
    - Övriga avgifter för rubrik
    - Övriga avgifter för rad
    - Kreditfaktura
    - Returorder
    - Inköpsrekvisition
    - Övriga avgifter för inköpsrekvisitionsrad
    - Anbudsförfrågan
    - Övriga avgifter för anbudsförfråganrubriken
    - Övriga avgifter för anbudsförfråganraden

- Lagerprocess

    - Överföringsorder - leverera
    - Överföringsorder - ta emot

## <a name="related-resources"></a>Relaterade resurser

[Kom i gång med skattetjänst](./global-get-started-with-tax-calculation-service.md)

[Flera momsregistreringsnummer](./emea-multiple-vat-registration-numbers.md)

[Skattefunktionsstöd för överföringsorder](./tasks/tax-feature-support-for-transfer-order.md)

[Så här skapar du tillägg i skattetjänst](./tax-service-add-data-fields-tax-integration-by-extension.md)