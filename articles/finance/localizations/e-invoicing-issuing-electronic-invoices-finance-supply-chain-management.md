---
title: Utfärda elektroniska fakturor i Finance och Supply Chain Management
description: I detta ämne beskrivs hur du utfärdar elektroniska fakturor i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management via tillägget Elektronisk fakturering.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 187f5a20d088b4fcd7af2a6576357a69c2efc2c6
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104439"
---
# <a name="issue-electronic-invoices-in-finance-and-supply-chain-management"></a>Utfärda elektroniska fakturor i Finance och Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

I detta ämne beskrivs hur du utfärdar elektroniska fakturor i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management via tillägget Elektronisk fakturering.


## <a name="feature-activation"></a>Funktionsaktivering

För att börja utfärda elektroniska fakturor via tillägget Elektronisk fakturering måste du aktivera funktionsreferensen i Finance och Supply Chain Management.

Varje funktionsreferens motsvarar en specifik funktion för elektronisk fakturering som överensstämmer med de elektroniska faktureringskraven från ett land eller en region.

Följande tabell visar en lista med funktionsreferenser som tillägget Elektronisk fakturering stöder.

| Funktionsreferens | Namn                                              | Land/region |
|-------------------|---------------------------------------------------|----------------|
| BR-00053          | NF-e Federal – brasiliansk elektronisk faktura       | Brasilien         |
| BR-00095          | NFS-e brasilianska elektroniska fakturor               | Brasilien         |
| DK-00001          | E-fakturering till offentlig sektor (OIOUBL) – DK    | Danmark        |
| EG-00008          | E-fakturering för Egypten                             | Egypten          |
| ES-00025          | Elektronisk faktura till den offentliga sektorn           | Spanien          |
| EUR-00023         | E-fakturering EU till offentlig sektor       | Europa         |
| ITA-00036         | IT – E-fakturering till offentlig sektor (FatturaPA) | Italien          |
| MX-00010          | E-fakturering CFDI                                  | Mexiko         |
| MX-00016          | E-fakturering CFDI – annulleringsprocess           | Mexiko         |

I de fall där det finns en äldre funktion för elektronisk fakturering som stöds av omfånget för nationslocalization, gör aktiveringen av funktionsreferensen det möjligt att utfärda elektroniska fakturor via tillägget Elektronisk fakturering och stänger av den tidigare funktionen.

## <a name="submit-electronic-documents"></a>Skicka in elektroniska dokument

Processen för att skicka in elektroniska dokument utgör en gemensam kommunikationspunkt mellan Finance och Supply Chain Management och tillägget Elektronisk fakturering. Vid varje sändningshändelse flödar kommunikationen i båda riktningar:

- **Från Finance och Supply Chain Management till tillägget Elektronisk fakturering** – Finance och Supply Chain Management skickar de abstrakta fakturorna till tillägget Elektronisk fakturering. De skickar vid behov även innehållet i variabler som konfigurerats som en del av de elektroniska faktureringsfunktionerna.
- **Från tillägget Elektronisk fakturering till Finance och Supply Chain Management** – Beroende på den elektroniska faktureringsfunktionen får Finance och Supply Chain Management uppdateringar från tillägget Elektronisk fakturering om bearbetningsresultaten av fakturor som skickats tidigare. De erhåller vid behov även innehållet i variabler som konfigurerats som en del av de elektroniska faktureringsfunktionerna.

Om du vill skicka elektroniska dokument till tillägget Elektronisk fakturering i EFinance and Supply Chain Management går du till **Organisationsadministration &gt; Periodisk &gt; Elektroniska dokument &gt; Skicka elektroniska dokument**.

Startpunkten är en bokförd faktura. Fakturan kan komma från olika ursprung, till exempel försäljningsorder, projektfakturor eller fritextfakturor.

Sändningsprocessen kan köras manuellt eller i bakgrunden.

- **Manuell körning** – För manuell körning måste du använda alternativet **Filter** för att definiera det dokumentintervall som måste skickas. På sidan **Filter** kan du konfigurera en egen fråga för att välja de bokförda fakturor som måste skickas. När valet är gjort måste du starta körningen manuellt och vänta tills den är klar. När bearbetningen är klar visar ett meddelande i Åtgärdscentret antalet elektroniska dokument som har skickats.
- **Bakgrundskörning** – Bakgrundskörningen körs utan att du måste vara inloggad eller hålla sändningsdialogrutan öppen. Du kan planera processen så att den körs och definiera körningsfrekvensen.

## <a name="view-the-submission-logs"></a>Visa överföringsloggarna

I Finance och Supply Chain Management kan du använda överföringsloggarna för att visa resultaten av bearbetningen av överföringen till tillägget Elektronisk fakturering. Gå till **Organisationsadministration &gt; Periodisk &gt; Elektroniska dokument &gt; Skicka elektroniska dokument**, och välj sedan ett värde i fältet **Dokumenttyp** för att filtrera den fakturatyp som loggarna anger.

Det finns tre möjliga sorters status för sändning:

- **Tidsplanerat** – Tillägget Elektronisk fakturering tog emot sändningen från Finance och Supply Chain Management, och bearbetningen av den elektroniska faktureringsfunktionen pågår.
- **Slutfört** – Tillägget Elektronisk fakturering bearbetade den elektroniska faktureringsfunktionen så som det konfigurerats för att köra den.
- **Misslyckat** – Tillägget Elektronisk fakturering påträffade ett fel eller stoppades av ett undantag under bearbetningen av den elektroniska faktureringsfunktionen.

> [!IMPORTANT]
> Sändningsstatusen refererar till statusen för den bearbetning som tillägget Elektronisk fakturering gör i den elektroniska faktureringsfunktionen. Den refererar inte till den slutliga statusen för själva den elektroniska fakturan.
>
> Om en elektronisk faktura till exempel måste skickas till en extern webbtjänst för godkännande, kan sändningsstatusen vara **Slutförd**, men statusen för den elektroniska fakturan vara **Avvisades**. I detta fall lyckades tillägget Elektronisk fakturering bearbetade den elektroniska faktureringsfunktionen då det konfigurerats för att bearbeta den funktionen. Den elektroniska fakturan avvisades dock eftersom den inte uppfyller de kriterier som webbtjänsten upprättat för fakturagodkännande.

Inlämningsloggarna innehåller följande ytterligare funktioner:

- **Inlämningsdetaljer** – Visa information om huvuduppgiften. I visualiseringen visas fullständig körningslogg för de åtgärder som konfigureras i den elektroniska faktureringsfunktionen. Det gör det också möjligt för användarna att hämta de filer som skapas under bearbetningen. I scenarier där fakturan måste godkännas av en extern webbtjänst kan användarna visa statusen för fakturan.
- **Relaterade inlämningar** – Visa information om underordnade inlämningar.
- **Annullera inlämningar** – Med denna funktion möjliggörs en särskild sändningsprocess i scenarier där den elektroniska fakturan måste godkännas av en extern webbtjänst. Funktionen instruerar tillägget Elektronisk fakturering att skicka ett specifikt meddelande till webbtjänsten med avsikten att annullera statusen för en godkänd elektronisk faktura i webbtjänstdatabasen.
- **Skicka om dokument** – Skicka om ett elektroniskt dokument som redan har skickats till tillägget Elektronisk fakturering. En helt ny logg skapas på sidan **Sändningsdetaljer**.
- **Skicka relaterade överföringar**
