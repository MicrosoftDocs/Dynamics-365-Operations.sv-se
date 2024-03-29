---
title: Designa ER-konfigurationer för att ignorera strukturlistetecken i genererade filer
description: I den här artikeln beskrivs hur du konfigurerar ett ER-format (elektronisk rapportering) för att generera rapporter som ignorerar byteordningsmärke.
author: kfend
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: EROperationDesigner
ms.openlocfilehash: a2ea132b51f2f451fbe81a9c7869bea84bf4017a
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324033"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a>Designa ER-konfigurationer för att ignorera strukturlistetecken i genererade filer

[!include [banner](../includes/banner.md)]

Du kan utforma [elektronisk rapportering (ER)](general-electronic-reporting.md) [lösning](er-quick-start1-new-solution.md) för att skapa utgående dokument. Om du vill generera dokumenten som text- eller XML-filer måste lösningen innehålla en ER [konfiguration](general-electronic-reporting.md#Configuration) som innehåller en komponent för ER format. Om du vill ange den [teckenkodning](/windows/win32/intl/character-sets) som representerar uppsättningen tecken i genererade filer måste ER-formatet innehålla formatelementet **Vanlig\\Fil**. Om du vill konfigurera ER-formatkomponenten måste du öppna versionen utkast för ER-konfigurationen i ER-formatdesignern och lägga till elementet **Vanlig\\Fil**. I fältet **kodning** ange kodning av utgående filer som genereras när programmet körs med hjälp av komponenten.

> [!NOTE]
> Om formatet innehåller fel kodningsnamn uppstår ett fel när du sparar ändringarna av formatets inställningar.

![Lägga till ett rotelement på sidan Formatdesigner.](./media/er-suppress-bom-characters-image1.gif)

Om du anger **UTF-8**, **UTF-16** eller **UTF-32** som kodning blir alternativet **Undertryck strukturlistetecken** tillgängligt. Ställ in det här alternativet på **Ja** för att undertrycka [byteordningsmärke (strukturlista) tecken](/globalization/encoding/byte-order-mark) i utgående filer som genereras vid körning när det redigerbara ER-formatet körs.

> [!NOTE]
> Om du lämnar fältet **Kodning** används standardvärdet **UTF-8**.

![Ange alternativet Ignorera strukturlistetecken på sidan Formatdesigner.](./media/er-suppress-bom-characters-image2.gif)

Om du vill granska funktionen vid körning ska du gå igenom lämplig procedur. Du kan till exempel utföra stegen i ämnet [Periodisera körning av XML-element i ER-format](er-defer-xml-element.md). När du har utfört stegen i avsnittet [Ändra formatet så att beräkningen baseras på genererade utdata](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) i det ämnet, följ dessa ytterligare steg.

1. Ange UTF-kodning:

    1. Välj elementet **Rapport** av typen **Vanlig\\Fil**.
    2. I fältet **Kodning** ange **UTF-8**-kodningen.

2. Generera en XML-fil som innehåller ett strukturlistetecken:

    1. Ange alternativet **Ignorera strukturlistetecken** till **Nej** om du vill inkludera strukturlistetecken i genererade XML-filer.
    2. Slutför stegen i avsnittet [Skjut upp körningen av sammanfattning XML-element så att den beräknade summan används](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) i ämnet [Skjuta upp körningen av XML-element i ER-format](er-defer-xml-element.md) och spara den genererade filen som **SampleXmlReport.xml**.

3. Generera en XML-fil som inte innehåller ett strukturlistetecken:

    1. Ange alternativet **Ignorera strukturlistetecken** till **Ja** om du vill undertrycka strukturlistetecken i genererade XML-filer.
    2. Slutför stegen i avsnittet [Skjut upp körningen av sammanfattning XML-element så att den beräknade summan används](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) i ämnet [Skjuta upp körningen av XML-element i ER-format](er-defer-xml-element.md) och spara den genererade filen som **SampleXmlReport (1).xml**.

4. Jämför de genererade filerna i ett filjämförelseverktyg.

    Den första skillnaden som du kommer att märka finns i filrubriken. Filen SampleXmlReport.xml innehåller ett strukturlistetecken, där SampleXmlReport(1).xml-filen inte finns.

    ![Jämför de genererade filerna med ett filjämförelseverktyg.](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a>Se även

- [Skjuta upp körningen av XML-element i ER-format](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
