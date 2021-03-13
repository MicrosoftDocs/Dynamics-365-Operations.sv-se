---
title: Utforma en ny ER-konfiguration för att generera rapporter i Word-format
description: I det här avsnittet beskrivs hur användare kan konfigurera ett nytt ER-format (elektronisk rapportering) för att generera rapporter som Microsoft Word-dokument.
author: NickSelin
manager: AnnBe
ms.date: 12/17/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 535e46eb033bf2796ab8e4b0d2e29767ad0a8cdf
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094164"
---
# <a name="design-a-new-er-configuration-to-generate-reports-in-word-format"></a>Utforma en ny ER-konfiguration för att generera rapporter i Word-format

[!include [banner](../includes/banner.md)]

Om du vill generera rapporter som Microsoft Word-dokument måste du designa en mall för rapporterna med hjälp av exempelvis Word-skrivbordsprogrammet. I följande bild visas exempelmallen för kontrollrapporten som kan genereras för att visa information om bearbetade leverantörsbetalningar.

![Exempelmall för kontrollrapporten i Word-skrivbordsprogrammet](./media/er-design-configuration-word-image1.png)

Om du vill använda ett Word-dokument som mall för rapporter i Word-format kan du konfigurera en ny [Elektronisk rapportering (ER)](general-electronic-reporting.md) [lösning](er-quick-start1-new-solution.md). Den här lösningen måste omfatta en ER [konfiguration](general-electronic-reporting.md#Configuration) som innehåller en komponent för ER [format](general-electronic-reporting.md#FormatComponentOutbound).

> [!NOTE]
> När du skapar en ny ER-formatkonfiguration för att generera rapporter i Word-format, måste du antingen välja **Word** som formattyp i dialogrutan **Skapa konfiguration** eller lämna fältet **Formattyp** tomt.

![Skapa en anpassad konfiguration av format på sidan konfigurationer](./media/er-design-configuration-word-image2.gif)

ER-formatkomponenten i lösningen måste innehålla ormatelementet **Excel\\Fil** och det formatelementet måste länkas till det Word-dokument som ska användas som mall för genererade rapporter vid körning. Om du vill konfigurera ER-formatkomponenten måste du öppna [utkast](general-electronic-reporting.md#component-versioning) versionen för den skapade ER-konfigurationen i ER-formatdesignern. Lägg sedan till elementet **Excel\\Fil**, koppla Word-mallen till det redigerbara ER-formatet och länka mallen till **Excel\\Fil** som du har lagt till.

> [!NOTE]
> När du bifogar en mall manuellt måste du använda en [dokumenttyp](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) som tidigare har [konfigurerats](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) i ER-parametrar för att lagra mallar i ER-format.

![Koppla en mall på sidan Formatdesigner](./media/er-design-configuration-word-image3.gif)

Du kan lägga till **Excel\\Intervall** och **Excel\\Cell** kapslade element för elementet **Excel\\Fil** om du vill ange strukturen för data som ska anges i genererade rapporter under körning. Därefter måste du knyta dessa element till datakällorna i det redigerbara ER-formatet för att ange de faktiska data som ska anges i genererade rapporter vid körning.

![Lägga till kapslade element på sidan Format designer](./media/er-design-configuration-word-image4.gif)

När du sparar ändringarna i ER-formatet vid tid för designen, lagras den hierarkiska formatstrukturen i den kopplade Word-mallen som en [anpassad XML-del](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019) med namnet **Rapport**. Du måste komma åt den ändrade mallen, hämta den från Finance, lagra den lokalt och öppna den i Word-skrivbordsprogrammet. I följande bild visas den lokalt lagrade exempelmallen för kontrollrapporten som innehåller den **rapport** anpassade XML-delen.

![Granska exempel rapportmallen i Word-skrivbordsprogrammet](./media/er-design-configuration-word-image5.gif)

När bindningar av formatelementen **Excel\\Intervall** och **Excel\\Cell** körs vid körning, data som varje bindning levererar kommer till det genererade Word-dokumentet som ett enskilt fält i anpassade XML-delen för **Rapport**. För att ange värdena från fälten för den anpassade XML-delen i ett genererat dokument måste du lägga till lämpligt Word [innehållskontroller](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) till din Word-mall som fungerar som platshållare för data som ska fyllas i när de körs. När du vill ange hur innehållskontroller ska fyllas i mappar du alla innehållskontroller till lämpligt fält i den anpassade XML-delen för **Rapport**.

![Lägga till och mappa innehållskontroller i Word-skrivbordprogrammet](./media/er-design-configuration-word-image6.gif)

Du måste sedan ersätta den ursprungliga Word-mallen i det redigerbara ER-formatet med den modifierade mallen som nu innehåller Word-innehållskontroller som har mappats till fälten i den anpassade XML-delen för **Rapport**.

![Ersätta en mall på sidan Formatdesigner](./media/er-design-configuration-word-image7.gif)

När du kör det konfigurerade ER-formatet används den kopplade Word-mallen för att generera en ny rapport. De faktiska data lagras i Word-rapporten som en anpassad XML-del med namnet **Rapport**. När den genererade rapporten öppnas fylls Word-innehållskontroller i med data från den anpassade XML-delen för **Rapport**.

## <a name="frequently-asked-questions"></a>Vanliga frågor

**Fråga:** Jag konfigurerat ett ER-format för att skriva ut ett Word-dokument som innehåller en företagsadress. I Word-mallen för det här ER-formatet infogade jag en RTF-innehållskontroll för att presentera en företagsadress. I Finance har jag angett företagsadressen som flerradstext och valt **Retur** om du vill lägga till en transportretur för varje rad jag angav. Därför förväntar jag mig att företagsadressen visas som flerradstext i genererade dokument. Adressen visas dock som en enskild textrad som innehåller särskilda symboler istället för returer. Vad är det för fel med inställningarna?

**Svar:** Istället för att använda en kontroll för innehåll med rik text måste du använda en kontroll för enkel textinnehåll och välja kryssrutan **Tillåt transportreturer (flera paragrafer)** i kontrollens egenskaper.

## <a name="additional-resources"></a>Ytterligare resurser

- [Återanvända ER-konfigurationer med Excel-mallar för att generera rapporter i Word-format](./tasks/er-design-configuration-word-2016-11.md)
- [Bädda in bilder och former i dokument som du skapar med ER](electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)
