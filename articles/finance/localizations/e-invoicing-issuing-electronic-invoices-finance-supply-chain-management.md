---
title: Utfärda elektroniska fakturor i Finance och Supply Chain Management
description: I detta ämne beskrivs hur du utfärdar elektroniska fakturor i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management via tillägget Elektronisk fakturering.
author: gionoder
manager: AnnBe
ms.date: 02/26/2021
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
ms.openlocfilehash: 099ebb56710e920f7b1453f32f23f59a80486ebf
ms.sourcegitcommit: 105f65468b45799761c26e5d0ad9df4ff162c38d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "5486963"
---
# <a name="issue-electronic-invoices-in-finance-and-supply-chain-management"></a>Utfärda elektroniska fakturor i Finance och Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

I detta ämne beskrivs hur du utfärdar elektroniska fakturor i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management via tillägget Elektronisk fakturering.


## <a name="feature-activation"></a>Funktionsaktivering

För att utfärda elektroniska fakturor via tillägget Elektronisk fakturering måste du aktivera funktionen i Finance och Supply Chain Management.

Varje funktion motsvarar en specifik funktion för elektronisk fakturering som överensstämmer med de elektroniska faktureringskraven för ett land eller en region.

Följande tabell visar en lista med funktionen som tillägget Elektronisk fakturering kan stödja.

| Namn                                              | Land/region |
|---------------------------------------------------|----------------|
|Österrikisk elektronisk faktura                        |Österrike         |
|Belgisk elektronisk faktura                         |Belgien         |
|NF-e Federal - brasiliansk elektronisk faktura       |Brasilien          |
|NFS-e – brasiliansk elektronisk faktura|Brasilien          |
|Dansk elektronisk faktura                          |Danmark         |
|Egyptisk elektronisk faktura                        |Egypten           |
|Estnisk elektronisk faktura                        |Estland         |
|Finsk elektronisk faktura                         |Finland         |
|Fransk elektronisk faktura                          |Frankrike          |
|Tysk elektronisk faktura                          |Tyskland         |
|PEPPOL – global elektronisk faktura                 |Globalt          |
|Italiensk elektronisk faktura                         |Italien           |
|CFDI – mexikansk elektronisk faktura                  |Mexiko          |
|Nederländsk elektronisk faktura                           |Nederländerna     |
|Norsk elektronisk faktura                       |Norge          |
|Spansk elektronisk faktura                         |Spanien           |

I de fall där det finns en äldre funktion för elektronisk fakturering som stöds av omfånget för nationslocalization, gör aktiveringen av dessa funktioner och gör det möjligt att aktivera elektroniska fakturor som utfärdas via tillägget Elektronisk fakturering.

> [!IMPORTANT]
> När funktionen för tillägg för elektronisk fakturering har aktiverats är den nya elektroniska faktureringsupplevelsen som standard inaktiverad. Du kan använda funktionsbegreppet när du selektivt vill aktivera nya erfarenheter för juridiska personer med hjälp av lands-/regionspecifika funktioner. Det alternativet **Global** styr den nya erfarenheten för de län/regioner som återstår och som inte specifikt listas i registret.

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
