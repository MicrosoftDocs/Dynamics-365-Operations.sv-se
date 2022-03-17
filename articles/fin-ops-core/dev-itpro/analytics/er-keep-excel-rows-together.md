---
title: Utforma ett ER-format för att hålla samman rader på samma Excel-sida
description: Det här ämnet förklarar hur du utformar ett elektroniskt rapporteringsformat (ER) som hållar ihop rader på samma Microsoft Excel-sida.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-03-01
ms.dyn365.ops.version: Version 10.0.26
ms.openlocfilehash: 711681ab38fb24b57a83f008f86a8261176aa5a5
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388607"
---
# <a name="design-an-er-format-to-keep-rows-together-on-the-same-excel-page"></a>Utforma ett ER-format för att hålla samman rader på samma Excel-sida

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Detta ämne beskriver hur en användare med rollen Systemadministratör eller Funktionskonsult för elektronisk rapportering kan konfigurera ett [format för elektronisk rapportering](general-electronic-reporting.md) [(ER)](er-overview-components.md#format-component) som genererar utgående dokument i Microsoft Excel samt elektronisk sidnumrering så att skapade rader hålls kvar på samma sida.

I det här exemplet ändrar du det Microsoft-tillhandahållna ER-format som används för att skriva ut fritextfakturor i Excel. Med dina ändringar kan du hantera sidnumreringen för en genererad fritextfakturarapport så att alla rader på en enskild fakturarad hålls kvar på samma sida när så är möjligt.

Procedurerna i detta ämne kan slutföras i företaget **USMF**. Ingen kod behövs.

I det här exemplet ska du skapa erforderliga ER-[konfigurationer](general-electronic-reporting.md#Configuration) för exempelföretaget **Litware, Inc.**. Se till att konfigurationsprovidern för exempelföretaget **Litware, Inc.** (`http://www.litware.com`) har listats för ER-ramverket samt att det har markerats som **Aktivt**. Om denna konfigurationsleverantör inte finns med i listan, eller om den inte är markerad som **Aktiv**, följer du stegen i [Skapa en konfigurationsleverantör och markera den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="enter-a-new-free-text-invoice"></a>Ange en ny fritextfaktura

1. Följ stegen i [Skapa en fritextfaktura](../../../finance/accounts-receivable/create-free-text-invoice-new.md#create-a-free-text-invoice-1) om du vill lägga till en fritextfaktura.

    1. Lägg till en enda rad i fakturan.
    2. Lägg till fem noteringar för fakturaraden.

    ![Granska fakturaradsnoteringar på sidan Bilagor.](./media/er-keep-excel-rows-together-notes.png)

2. Följ stegen i [Kopiera rader](../../../finance/accounts-receivable/create-free-text-invoice-new.md#copy-lines) om du vill skapa ytterligare fem fakturarader som kopierar fakturaraden som du lade till i föregående steg.

    ![Granska fritextfakturaraderna på fritextfakturasidan.](./media/er-keep-excel-rows-together-invoice.png)

## <a name="configure-the-er-framework"></a>Konfigurera ER-ramverket

Följ stegen i [Konfigurera ER-ramverket](er-quick-start2-customize-report.md#ConfigureFramework) för att ställa in den minimala uppsättningen ER-parametrar. Du måste slutföra de här inställningarna innan du börjar använda ER-ramverket för att designa en anpassad version av ett standard-ER-format.

## <a name="import-the-standard-er-format-configuration"></a>Importera standardkonfiguration av ER-format

Följ anvisningarna i [Importera standardkonfigurationen för ER -format](er-quick-start2-customize-report.md#ImportERSolution1) för att lägga till standard ER -konfigurationer i din nuvarande instans av Dynamics 365 Finance. Till exempel importversion **252.116** av formatkonfigurationen **Fritextfaktura (Excel)**. Basversion **252** av konfigurationen för **grundfakturamodell** importeras automatiskt från databasen tillsammans med den konfiguration av **fakturamodellmappningen** som krävs.

## <a name="set-up-print-management-to-use-the-standard-er-format"></a>Ställa in utskriftshantering för användning av standardformat för ER

Följ stegen i [Konfigurerar utskriftshantering](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement1) för att konfigurera utskriftshantering för modulen **Kundreskontra** så att ER-standardformatet används för utskrift av fritextfakturor.

## <a name="configure-a-format-destination-for-the-standard-er-format"></a>Konfigurera en formatdestination för ER-standardformatet

Följ stegen i [Konfigurera en formatdestination för förhandsgranskning på skärmen](er-quick-start1-new-solution.md#ConfigureDestination) om du vill konfigurerar ER-målet [Skärm](er-destination-type-screen.md) för ER-standardformatet så att genererade rapporter konverteras till PDF-format och förhandsgranskas på en ny webbläsarflik.

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a>Skriv ut en fritextfaktura med hjälp av ER-standardformatet

1. Följ stegen i [Skriv ut en fritextfaktura](er-embed-images-header-footer-excel-reports.md#ProcessInvoice1) om du vill använda ER_standardformatet för att generera en fritextfakturarapport i Excel-format för den tillagda fakturan.
2. Hämta den genererade Excel-arbetsboken och granska den i det stationära Excel-programmet.

    Lägg märke till att den sjätte raden i fakturan börjar på första sidan i rapporten och fortsätter på den andra sidan. Den sista noteringen visas på den andra sidan, och det är inte uppenbart att den hör till den sjätte fakturaraden. Därför gör sidbrytningen i mitten av innehållet för fakturaraden detta dokument mer svårläsligt.

    ![Granska sidnumreringen för den genererade fritextfakturan i det stationära Excel-programmet.](./media/er-keep-excel-rows-together-invoice1.gif)

Återstående procedurer i detta ämne visar hur du kan finjustera ER-standardformatet för att förbättra utseendet och läsbarheten i fakturarapporten genom att behålla allt innehåll för en enskild fakturarad på samma sida.

## <a name="create-a-custom-format"></a>Skapa ett anpassat format

Följ stegen i [Skapa ett eget format](er-embed-images-header-footer-excel-reports.md#DeriveProvidedFormat) om du vill härleda ett format från det importerade ER-formatet och skapa en ER-konfiguration i form av en **anpassad fritextfaktura (Excel)** som är tillgänglig för redigering och ändring.

## <a name="edit-the-custom-format"></a>Redigera anpassat format

1. Följ stegen i [Skapa ett eget format](er-embed-images-header-footer-excel-reports.md#ConfigureDerivedFormat) för att öppna det härledda ER-formatet för redigering i ER-formatdesignern.
2. På sidan **Formatdesigner**, i formatkomponentträdet i vänstra fönstret, expanderar du **Fritextfaktura \> Ark \> Fakturarader** och väljer komponenten **InvoiceLines_Values**.
3. Under fliken **Format** ställer du in alternativet **Håll ihop rader** som **Ja**.

    ![Ställa in alternativet Behåll rader tillsammans för det redigerbara ER-formatet på sidan Formatdesigner.](./media/er-keep-excel-rows-together-format.png)

4. Markera **Spara** och stäng sedan sidan.

## <a name="mark-the-custom-format-as-runnable"></a>Markera det anpassade formatet som körbart

Följ stegen i [Markera det anpassade formatet som körbart](er-embed-images-header-footer-excel-reports.md#MarkFormatRunnable) om du vill göra den ändrade versionen av det anpassade ER-formatet körbart.

## <a name="set-up-print-management-to-use-the-custom-er-format"></a>Konfigurera utskriftshantering för användning av ER-standardformatet

Följ stegen i [Konfigurera utskriftshantering](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement2) för att konfigurera utskriftshantering för modulen **Kundreskontra** så att ER-standardformatet används för utskrift av fritextfakturor.

## <a name="configure-a-format-destination-for-the-custom-er-format"></a>Konfigurera en formatdestination för anpassat ER-format

Följ stegen i [Konfigurera en formatdestination för förhandsgranskning på skärmen](er-quick-start1-new-solution.md#ConfigureDestination) om du vill konfigurera ER-destinationen **Skärm** för anpassat ER-format så att genererade rapporter konverteras till PDF-format och förhandsgranskas på en ny webbläsarflik.

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a>Skriv ut en fritextfaktura med hjälp av det anpassade ER-standardformatet

1. Följ stegen i [Skriv ut en fritextfaktura](er-embed-images-header-footer-excel-reports.md#ProcessInvoice2) om du vill använda det anpassade ER-formatet för att generera en fritextfakturarapport i Excel-format för den tillagda fakturan.
2. Hämta den genererade Excel-arbetsboken och granska den i det stationära Excel-programmet.

    Lägg märke till att den sjätte raden i fakturan startar på den andra sidan och att alla Excel-rader som representerar den här fakturaraden visas tillsammans på den sidan.

    ![Granska den uppdaterade sidnumreringen för den genererade fritextfakturan i det stationära Excel-programmet.](./media/er-keep-excel-rows-together-invoice2.gif)

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa en konfiguration för att generera dokument i Excel-format](er-fillable-excel.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
