---
title: Skatteberäkningstjänst (förhandsversion)
description: Det här ämnet innehåller information om beräkningstjänstens övergripande omfattning och funktioner.
author: wangchen
ms.date: 03/02/2021
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
ms.openlocfilehash: 518d3fda7b97e55d23beea6a1ba0e50b44a7aa0e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818234"
---
# <a name="tax-calculation-service-preview"></a>Skatteberäkningstjänst (förhandsversion)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Momsberäkningstjänsten är en hyperskalbar tjänst för flera innehavare som gör det möjligt för global tax engine att automatisera och förenkla bestämmandet av skatt och beräkningsprocessen. Skattemotorn är helt konfigurerbar. Elementen som kan konfigureras är inklusive, men inte begränsat till, den momsbara datamodellen, momskoden, tillämplighetsmatrisen för moms och beräkningsformeln för skatt. Momsmotorn körs på Microsoft Azure kärntjänsters plattform och erbjuder modern teknik och exponentiell skalbarhet.

Beräkningstjänsten för moms går att integrera med Dynamics 365 Finance och Dynamics 365 Supply Chain Management. Så småningom kommer den också att integreras Dynamics 365 Project Operations, Dynamics 365 Commerce och andra applikationer från första och tredje part.

Momsberäkningstjänsten är en Microsoft-baserad momsmotor som erbjuder exponentiell skalbarhet. Det kan hjälpa dig att utföra följande uppgifter:

- Konfigurera beräkningstjänsten för skatt via Regulatory Configuration Service (RCS). RCS är en förbättrad version av designern Elektronisk rapportering (ER) och är tillgänglig som en fristående tjänst.
- Konfigurera momsmatrisen om du automatiskt vill bestämma momskoder och momssatser.
- Konfigurera momsmatrisen om du automatiskt vill bestämma momsregistreringsnummer.
- Konfigurera designern för momsberäkning om du vill definiera formler och villkor.
- Dela lösningen för skattebestämning och beräkning mellan juridiska personer.

Om du vill använda beräkningstjänsten för moms ska du installera tillägget för skatteberäkningstjänsten från projektet i Microsoft Dynamics Lifecycle Services (LCS). Slutför sedan inställningarna i RCS och aktivera skatteberäkningstjänsten i Finance och Supply Chain Management. För mer information, se [Kom igång med momstjänsten](https://go.microsoft.com/fwlink/?linkid=2138482).

## <a name="availability"></a>Tillgänglighet

Skatteberäkningstjänsten är bara tillgänglig i arbetsmiljöer och för valda kunder, via ett public preview-program. Så småningom blir den allmänt tillgänglig för alla kunder och i produktionsmiljöer.

Nya funktioner kommer även fortsättningsvis att levereras i skatteberäkningstjänsten. Kontrollera därför den senaste dokumentationen ofta för att ta reda på disponering och område som stöds av funktionerna.

Momsberäkningstjänsten distribueras i följande geologier för Azure. Den kommer även att distribueras till fler Azure-geologer, baserat på kundernas behov:

- USA
- Europa
- Frankrike
- Storbritannien

> [!NOTE]
> Beräkningstjänsten för moms har inte stöd för lokala distributioner av Dynamics 365. Den stöder inte heller tidigare versioner, till exempel Dynamics AX 2012.

## <a name="feature-highlights"></a>Funktionens höjdpunkter

- Konfigurera momsmatrisen om du automatiskt vill bestämma och beräkna skatt
- Stöd för flera momsregistreringsnummer
- Överföringsorderstöd för bestämning och beräkning av skatter
- Överföringsorder för att bestämma flera momsregistreringsnummer

## <a name="supported-transactions"></a>Transaktioner som stöds

Beräkningstjänsten för moms kan aktiveras av juridisk person och transaktion. Följande transaktioner stöds:

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

[Kom i gång med momstjänst](https://go.microsoft.com/fwlink/?linkid=2138482)

[Flera momsregistreringsnummer](https://go.microsoft.com/fwlink/?linkid=2153387)

[Momsfunktionens stöd för överföringsorder](https://go.microsoft.com/fwlink/?linkid=2153388)

[Så här bygger du anknytning i momstjänst](https://go.microsoft.com/fwlink/?linkid=2138483)
