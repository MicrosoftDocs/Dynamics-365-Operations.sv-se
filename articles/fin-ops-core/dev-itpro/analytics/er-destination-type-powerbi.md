---
title: Power BI ER-målstyper
description: Det här avsnittet innehåller information om hur du konfigurerar Power BI ER-måltyp för utgående dokument.
author: NickSelin
manager: AnnBe
ms.date: 01/23/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 10.0.09
ms.openlocfilehash: 9202e8e9ca11f7f0159287b52495a923297c6ed6
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020009"
---
# <a name="PowerBIDestinationType">Power BI-destination</a>

[!include [banner](../includes/banner.md)]

Du kan konfigurera ett Microsoft Power BI-destination för varje mapp- eller filkomponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument. Baserat på destinationsinställningen lagras ett genererat dokument i en tidigare konfigurerad SharePoint-mapp.

Ange **Aktiverad** till **Ja** om du vill använda din ER-konfiguration för att ordna överföringen av data från din Dynamics 365 Finance-instans till Microsoft Power BI-tjänster. De överförda filerna lagras i en Microsoft SharePoint-serverinstans som måste ha konfigurerats för det syftet. Mer information finns i [Konfigurera elektronisk rapportering (ER) för att hämta data till Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md).

[![Sidan Destinationsinställningar](./media/ER_Destinations-EnablePowerBIDestination.png)](./media/ER_Destinations-EnablePowerBIDestination.png)

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)
- [Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)
