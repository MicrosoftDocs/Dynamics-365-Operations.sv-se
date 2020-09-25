---
title: ER-målstyp för e-post
description: Det här ämnet ger information om hur du konfigurerar en e-postdestination för varje MAPP- eller FIL-komponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 72f67ad915ba2acc90ecb52bdb97e42504450a03
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745571"
---
# <a name="email-destination"></a>E-postmål

[!include [banner](../includes/banner.md)]

Du kan konfigurera en e-postdestination för varje MAPP- eller FIL-komponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument. Baserat på destinationsinställningen lagras ett levererat dokument som en bilaga till ett e-postmeddelande.

Ställ in **Aktiverad** till **Ja** för att skicka en utdatafil via e-post. När det här alternativet är aktiverat kan du ange e-postmottagare samt redigera e-postmeddelandets ämne och brödtext. Du kan skapa konstanta texter mailets rubrik och brödtext, eller använda ER-[formler](er-formula-language.md) för att skapa e-posttexter dynamiskt. 

Du kan konfigurera e-postadresser för ER på två sätt. Konfigurationen kan slutföras på samma sätt som funktionen utskriftshanterings slutför den, eller så kan du lösa en e-postadress genom att använda en direkt referens till ER-konfigurationen via en formel.

[![Aktivera e-postmål](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="email-address-types"></a>E-postadresstyper

När du klickar på **Redigera** för fältet **Till** eller **Cc**, visas dialogrutan **E-posta**. Du kan sedan välja vilken typ av e-postadress som ska användas. E-posttyperna **Konfigurations-e-postmeddelande** och **Utskriftshantering** stöds för närvarande.

[![Välj typ av e-post](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management"></a>Utskriftshantering

Om du väljer typen **Utskriftshantering för e-postmeddelanden** kan du ange fasta e-postadresser i fältet **Till**. 

[![Konfigurera fasta e-postadresser](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)

Du måste välja källtyp för e-postmeddelanden till en filmål om du vill använda e-postadresser som inte är fasta. Följande värden kan användas: **Kund**, **Leverantör**, **Potentiell kund**, **Kontakt**, **Konkurrent**, **Arbetare**, **Sökande**, **Potentiell leverantör** samt **Otillåten leverantör**. När du har valt en e-posttyp klickar du på knappen bredvid fältet **Källkonto för e-post** för att öppna formuläret **Formeldesigner**. Du kan använda det här formuläret för att bifoga en formel som returneras vid körningen **partskonto** för den valda källtypen från det bearbetade dokumentet till e-postmålet.

[![Konfigurera källkonto för e-post](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)

Formlerna är specifika för ER-konfigurationen. Ange en dokumentspecifik referens till en kund- eller leverantörsparttyp i fältet **Formel**. I stället för skriva in datakällanoden kan du hitta den som representerar kund- eller leverantörskontot och klicka på **Lägg till datakälla** om du vill uppdatera formeln. Exempel: Om du använder konfigurationen **ISO 20022 för kreditöverföring** är noden som representerar ett leverantörskonto `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

Om du anger ett strängvärde, t.ex. `"DE-001"` och sparar en formel, skickas ett e-postmeddelande till leverantörens kontaktperson **DE-001**.


[![Sidan ER-formeldesigner](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)

[![Konfigurera källattributkonto för e-post](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)



### <a name="configuration-email"></a>Konfigurations-e-postmeddelande

Använd den här typen av e-post om den konfiguration som du använder har en nod i datakällorna som representerar en **e-postadress**. Du kan använda datakällor och funktioner i formeldesignern för att få en korrekt formaterad e-postadress. Exempel: Om du använder konfigurationen **ISO 20022 kreditöverföring** är noden som representerar en e-postadress för leverantörens kontaktperson `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Konfigurera målkonto för e-post](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)
- [Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)
- [Formeldesigner i elektronisk rapportering (ER)](general-electronic-reporting-formula-designer.md)
