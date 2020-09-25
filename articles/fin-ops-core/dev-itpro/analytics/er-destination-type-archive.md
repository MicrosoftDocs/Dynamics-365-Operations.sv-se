---
title: Arkivera ER-målstyp
description: Det här ämnet ger information om hur du konfigurerar en arkivdestination för varje MAPP- eller FIL-komponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument.
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
ms.openlocfilehash: 8797a68507a5116c6adbf1f2d805838fa507958c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745595"
---
# <a name="archive-destination"></a>Arkivmål

[!include [banner](../includes/banner.md)]

Du kan konfigurera en arkivdestination för varje MAPP- eller FIL-komponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument. Baserat på destinationsinställningen lagras ett genererat dokument som en bilaga till en post i ER-jobblistan.

Du kan använda detta alternativ för att skicka de genererade dokumentet till en Microsoft SharePoint-mapp eller till Microsoft Azure Storage. Ställ in **Aktiverad** till **Ja** för att skicka utdata till en mål som definierats av den valda dokumenttypen. Endast dokumenttyper där gruppen är inställd på **Fil** kan väljas. Du kan ange dokument [typer](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) på **Organisationsadministration** \> **Dokumenthantering** \> **Dokumenttyper**. Konfigurationen för ER-mål är samma som konfigurationen för dokumenthanteringssystemet.

[![Sida för dokumenttyper](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)

Platsen avgör var filen sparas. När målen **Arkiv** har aktiverats kan resultaten sparas i jobbarkivet. Du kan visa resultaten via **Organisationsadministration** \> **Elektronisk rapportering** \> **Arkiverade elektroniska rapporteringsjobb**.

> [!NOTE]
> Välj en dokumenttyp för jobbarkivet genom att navigera till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering** \> **Parametrar för elektronisk rapportering**. Mer information finns i [Konfigurera ramverket för elektronisk rapportering (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).

## <a name="sharepoint"></a>SharePoint

Du kan spara en fil i en viss SharePoint-mapp. Du definierar standard SharePoint-server via **Organisationsadministration** \> **Dokumenthantering** \> **Dokumenthanteringsparametrar**. På fliken **SharePoint**, konfigurera SharePoint-mappen. Sedan kan du välja den mapp där ER-utdata ska sparas. **SharePoint**-platsen måste väljas i dokumenttypen.

[![Markera SharePoint-mappen](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)

## <a name="azure-storage"></a>Azure Storage

När dokumenttypens plats är inställd på **Azure Storage** kan du spara en fil i Azure Storage.

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)
- [Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)
- [Konfigurera dokumenthantering](../../fin-ops/organization-administration/configure-document-management.md)
