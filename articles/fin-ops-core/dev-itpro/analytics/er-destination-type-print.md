---
title: ER-målstyp för skrivare
description: I den här artikeln beskrivs hur du konfigurerar en skrivare för varje MAPP- eller FIL-komponent i ett elektroniskt rapporteringsformat (ER).
author: kfend
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423
ms.assetid: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: 7e01476b85c6c35d7c36c90db4d64ab2a2930fec
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271747"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>Skrivardestination

[!include [banner](../includes/banner.md)]

Du kan skicka ett genererat dokument direkt till en nätverksskrivare för direkt utskrift.

## <a name="prerequisites"></a>Förutsättningar

Innan du börjar måste du installera och konfigurera dokumentflödesagenten och sedan registrera nätverksskrivarna. Mer information finns i [Installera dokumentflödesagenten för att aktivera nätverksutskrift](./install-document-routing-agent.md).

## <a name="make-the-printer-destination-available"></a>Göra skrivarmålet tillgängligt

Om du vill göra **skrivarmålet** tillgängligt i den aktuella instansen av Microsoft Dynamics 365 Finance, gå till arbetsytan **Funktionshantering** och aktiverar följande funktioner i den här ordningen:

1. Konvertera utgående dokument för elektronisk rapportering från Microsoft Office-format till PDF.
2. Dokumentflödesagenten som mål för utgående dokument vid elektronisk rapportering

[![Aktivera funktionen för ER-skrivarmål i funktionshanteringen.](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Tillämplighet

#### <a name="pdf-printing"></a>PDF-utskrift

I versioner av Ekonomi före 10.0.18 kan målet **Skrivare** konfigureras endast för filkomponenter som används för att generera utdata i utskriftsbart PDF-format (formatelementen **PDF-sammanfogning** eller **PDF-fil**) eller Microsoft Office Excel- och Word-format (**Excel-fil**-formatelement). När utdata genereras i PDF-format skickas det till en skrivare. När utdata genereras i Office-format genom att använda formatelementet **Excel-fil** konverteras det automatiskt till PDF-format och skickas sedan till en skrivare.

Från och med version 10.0.18 kan du konfigurera målet **Skrivare** för formatelementet **Vanlig fil**. Detta formatelement används oftast för att generera utdata i antingen TXT- eller XML-format. Du kan konfigurera ett ER-format som innehåller formetelementet **Vanlig fil** som rotformatelement och formatelementet **Binära innehåll** som det enda kapslade elementet under det. I detta fall producerar formatelementet **Vanlig fil** utdata i det format som anges av den bindning som du konfigurerar för formatet **Binära innehåll**. Du kan till exempel konfigurera denna bindning som [fyll i](tasks/er-document-management-files-5.md#modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format) detta element med innehållet i en bilaga för [dokumenthantering](../../fin-ops/organization-administration/configure-document-management.md) i PDF- eller Office-format (Excel eller Word). Du kan skriva ut utdata genom att använda det konfigurerade målet **Skrivare**. 

> [!NOTE]
> När du väljer formatelementet **Vanlig\\Fil** för att konfigurera målet **Skrivare** går det inte att garantera (i samband med design) att det valda elementet producerar utdata i PDF-format eller utdata som kan konverteras till PDF-format. Därför visas följande varningsmeddelande: "Se till att den utdata som genereras av den valda formatkomponenten kan konverteras till PDF. Annars avmarkerar du alternativet "Konvertera till PDF". Du måste vidta åtgärder för att förhindra körningsproblem när utdata som inte är PDF eller PDF-konvertera utdata ska skrivas ut vid körning. Om du förväntar dig att få utdata i Office-formatet (Excel eller Word) måste alternativet **Konvertera till PDF** vara valt.
>
> Om du vill använda alternativet **Konvertera till PDF** i version 10.0.26 eller senare måste du välja **PDF** för parametern **Dokumentdirigeringstyp** för konfigurerat **Skrivar**-mål.

#### <a name="zpl-printing"></a>ZPL-utskrift

I version 10.0.26 och senare kan du konfigurera målet **Skrivare** för formatelementet **Vanlig\\Fil** genom att välja **ZPL** för parametern **Dirigeringstyp för dokument**. I det här ignoreras alternativet **Konfigurera till PDF** vid körning, och TXT- eller XML-utdatan skickas direkt till en vald skrivare genom att använda ZPL-avtalet (Zebra Programming Language) i [Dokumentflödesagenten (DRA)](install-document-routing-agent.md). Använd den här funktionen för ett ER-format som representerar en ZPL II-etikettlayout för utskrift av olika etiketter.

[![Ange parametern Dokumentdirigeringstyp i dialogrutan Målinställningar.](./media/ER_Destinations-SetDocumentRoutingType.png)](./media/ER_Destinations-SetDocumentRoutingType.png)

Mer information om den här funktionen finns i [Designa en ny ER-lösning för utskrift av ZPL-etiketter](er-design-zpl-labels.md).

### <a name="limitations"></a>Begränsningar

**Skrivarmålet** implementeras endast för molndistributioner.

### <a name="use-the-printer-destination"></a>Använd skrivarmål

1. Ställ in alternativet **aktiverade** till **Ja** om du vill skicka ett genererat dokument till en skrivare.
2. I fältet **Skrivarnamn** välj önskad nätverksskrivare.
3. Ange alternativet **Spara i utskriftsarkivet?** till **Ja** att de genererade utdata ska sparas i utskriftsarkivet så att de blir tillgängliga för utskriften. Om du vill komma åt arkiverade utdata senare **Organisationsadministration** \> **Förfrågningar och rapporter** \> **Rapportarkiv**.

[![Använda skrivarmål.](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> Alternativet **konvertera till PDF** måste inte vara aktiverat när du konfigurerar **skrivarmålet**. PDF-konverteringen för utskrift sker även om alternativet är inaktiverat.

För att använda en specifik [sidorientering](electronic-reporting-destinations.md#SelectPdfPageOrientation) när du skriver ut ett utgående dokument i Excel-format måste du aktivera alternativet **Konvertera till PDF**. När du ställer in alternativet **Konvertera till PDF** till **Ja** blir fältet **Sidorientering** blir tillgängligt. Välj önskad **sidorientering** i fältet kan du välja sidorientering.

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)
- [Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
