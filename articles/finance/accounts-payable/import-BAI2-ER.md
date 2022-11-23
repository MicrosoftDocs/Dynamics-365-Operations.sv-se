---
title: Skapa avancerad bankavstämningsimport med hjälp av elektronisk rapportering
description: Detta ämne innehåller information om hur du använder elektronisk rapportering när du konfigurerar den avancerade importprocessen.
author: angelad116
ms.date: 03/30/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: bfc1c2021387ed35e6ccb513167e896eddef2eaf
ms.sourcegitcommit: ea79bf014bbf495ac8e28db29502c8bd85a75f32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2022
ms.locfileid: "9759611"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Skapa avancerad bankavstämningsimport med hjälp av elektronisk rapportering

[!include [banner](../includes/banner.md)]

Funktionen för avancerad bankavstämning låter dig importera elektroniska bankutdrag och utföra en automatiskt avstämning mot banktransaktioner i Microsoft Dynamics 365 Finance. Den här artikeln innehåller en beskrivning av hur du ställer in importfunktionen för bankutdrag. Inställningen för import av bankutdrag varierar beroende på formatet på det elektroniska bankutdraget. Microsoft Dynamics 365 Finance stöder tre färdiga format för bankutdrag: ISO20022, MT940 and BAI2. 

## <a name="set-up-the-electronic-reporting-configuration"></a>Ställa in konfigurationen för elektronisk rapportering

1. Gå till **Arbetsytor \> Elektronisk rapportering**.
2. På panelen för **Microsoft**-konfigurationsprovidern väljer du **Databaser**.
3. Markera **Global** och välj sedan **Öppna**.
4. Om en anslutning till databasen måste upprättas väljer du den blå länken i dialogrutan.
5. I konfigurationslistan söker du upp **Avancerad modell för bankavstämningsutdrag \> ABR BAI2-format**.
6. Välj formatet **BAI2**.
7. På snabbfliken **Versioner** väljer du den senaste versionen och sedan **Importera**.

>[!NOTE]
>**BAI2-bankutdragsmodell** inaktiveras senare. 

## <a name="set-up-the-bank-statement-format"></a>Konfigurera formatet för bankutdrag

1. Gå till **Kassa- och bankhantering \> Inställningar \> Inställningar för avancerad bankavstämning \> Bankutdragsformat**.
2. Välj **Ny**.
3. Konfigurera fälten **Utdragsformat** och **Namn**.
4. Markera kryssrutan **Allmänt elektroniskt importformat**.
5. Ange fältet **Konfiguration för importformat** som formatet **BA12**.

## <a name="set-up-the-bank-account"></a>Konfigurera bankkontot

1. Gå till **Kassa- och bankhantering \> Bankkonton \> Bankkonton**.
2. Öppna bankkontot.
3. Pån snabbfliken **Avstämning** ställer du in alternativet **Avancerad bankavstämning** som **Ja**.
4. Ställ in fältet **Utdragsformat** på det **BAI2-format** som du skapade tidigare.

## <a name="import-the-bank-statement"></a>Importera bankutdrag

1. Gå till **Kassa- och bankhantering \> Avstämning av bankutdrag \> Bankutdrag**.
2. På sidan **Bankutdrag** väljer du **Importera utdrag**.
3. Ställ in fältet **Bankkonto** till det bankkonto som angetts i utdraget.
4. Ställ in fältet **Utdragsformat** på det **BAI2-format** som du skapade tidigare.
5. Välj **Bläddra** och välj filen **BAI**.
6. Välj **överför**.
7. Välj **OK** för att importera den valda filen.


## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Exempel på bankutdragsformat och tekniska layouter
Nedan visas exempel på layoutdefinitioner för den avancerade bankavstämningimportfilen samt tre relaterade exempel på bankutdragsfiler: [Exempel på importfil](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Teknisk layoutdefinition                             | Bankutdragsexempelfil          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)     |
| DynamicsAXISO20022Layout | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)     |

