---
title: ER-målstyp för skrivare
description: I det här avsnittet beskrivs hur du konfigurerar en skrivare för varje MAPP- eller FIL-komponent i ett elektroniskt rapporteringsformat (ER).
author: NickSelin
ms.date: 02/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 83081f8c17a903cd447a34596df2e61ebda0cafc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753442"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>Skrivardestination

[!include [banner](../includes/banner.md)]

Du kan skicka ett genererat dokument direkt till en nätverksskrivare för direkt utskrift.

## <a name="prerequisites"></a>Förutsättningar

Innan du börjar måste du installera och konfigurera dokumentflödesagenten och sedan registrera nätverksskrivarna. Mer information finns i [Installera dokumentflödesagenten för att aktivera nätverksutskrift](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).

## <a name="make-the-printer-destination-available"></a>Göra skrivarmålet tillgängligt

Om du vill göra **skrivarmålet** tillgängligt i den aktuella instansen av Microsoft Dynamics 365 Finance, gå till arbetsytan **Funktionshantering** och aktiverar följande funktioner i den här ordningen:

1. Konvertera utgående dokument för elektronisk rapportering från Microsoft Office-format till PDF.
2. Dokumentflödesagenten som mål för utgående dokument vid elektronisk rapportering

[![Aktivera funktionen för ER-skrivarmål i funktionshantering](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Tillämplighet

**Skrivarmålet** kan bara konfigureras för de fil komponenter som används för att generera utdata i antingen utskrivbara PDF-format (PDF-sammanslagning eller PDF-filformat) eller Microsoft Office Excel/Word-format (Excel-fil). När utdata genereras i PDF-format skickas det till en skrivare. När utdata genereras i Microsoft Office-format konverteras det automatiskt till PDF-format och skickas sedan till en skrivare.

### <a name="limitations"></a>Begränsningar

**Skrivarmålet** implementeras endast för molndistributioner.

### <a name="use-the-printer-destination"></a>Använd skrivarmål

1. Ställ in alternativet **aktiverade** till **Ja** om du vill skicka ett genererat dokument till en skrivare.
2. I fältet **Skrivarnamn** välj önskad nätverksskrivare.
3. Ange alternativet **Spara i utskriftsarkivet?** till **Ja** att de genererade utdata ska sparas i utskriftsarkivet så att de blir tillgängliga för utskriften. Om du vill komma åt arkiverade utdata senare **Organisationsadministration** \> **Förfrågningar och rapporter** \> **Rapportarkiv**.

[![Använd skrivarmål](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> Alternativet **konvertera till PDF** måste inte vara aktiverat när du konfigurerar **skrivarmålet**. PDF-konverteringen för utskrift sker även om alternativet är inaktiverat.

För att använda en specifik [sidorientering](electronic-reporting-destinations.md#SelectPdfPageOrientation) när du skriver ut ett utgående dokument i Excel-format måste du aktivera alternativet **Konvertera till PDF**. När du ställer in alternativet **Konvertera till PDF** till **Ja** blir fältet **Sidorientering** blir tillgängligt. Välj önskad **sidorientering** i fältet kan du välja sidorientering.

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)
- [Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
