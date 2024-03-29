---
title: Arkivera ER-målstyp
description: Det här ämnet innehåller information om hur du konfigurerar en arkivdestination för varje MAPP- eller FIL-komponent i ett ER-format (elektronisk rapportering).
author: kfend
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 97423
ms.assetid: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: d907bf391c0629d62da489cea90a05eabaf69ef1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285468"
---
# <a name="archive-er-destination-type"></a>Arkivera ER-målstyp

[!include [banner](../includes/banner.md)]

Du kan konfigurera en arkivdestination för varje **Mapp**- eller **Fil**-komponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument. Baserat på destinationsinställningen lagras ett genererat dokument som en bilaga till en post i ER-jobblistan. Visa resultaten genom att gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Arkiverade elektroniska rapporteringsjobb**.

Du kan använda detta alternativ för att skicka de genererade dokumentet till en Microsoft SharePoint-mapp eller till Microsoft Azure Storage. Ställ in **Aktiverad** till **Ja** för att skicka utdata till en mål som definierats av den valda dokumenttypen. Endast dokumenttyper där gruppen är inställd på **Fil** kan väljas. Du kan ange dokument [typer](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) på **Organisationsadministration** \> **Dokumenthantering** \> **Dokumenttyper**. Konfigurationen för ER-mål är samma som konfigurationen för dokumenthanteringssystemet.

[![Sida för dokumenttyper.](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)

Platsen avgör var filen sparas. När målen **Arkiv** har aktiverats kan resultaten sparas i jobbarkivet. Du kan visa resultaten via **Organisationsadministration** \> **Elektronisk rapportering** \> **Arkiverade elektroniska rapporteringsjobb**.

> [!NOTE]
> Välj en dokumenttyp för jobbarkivet genom att navigera till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering** \> **Parametrar för elektronisk rapportering**. Mer information finns i [Konfigurera ramverket för elektronisk rapportering (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).

## <a name="sharepoint"></a>SharePoint

Du kan spara en fil i en viss SharePoint-mapp. Du definierar standard SharePoint-server via **Organisationsadministration** \> **Dokumenthantering** \> **Dokumenthanteringsparametrar**. På fliken **SharePoint**, konfigurera SharePoint-mappen. Sedan kan du välja den mapp där ER-utdata ska sparas. **SharePoint**-platsen måste väljas i dokumenttypen.

[![Markera en SharePoint-mapp.](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)

## <a name="azure-storage"></a>Azure Storage

När dokumenttypens plats är inställd på **Azure Storage** kan du spara en fil i Azure Storage.

> [!NOTE] 
> I ER-ramverket lagras filer permanent i Azure blobminne till skillnad från ramverket för datahantering som tillämpar den bevarande principen om sju dagar för dokument som måste bearbetas. Mer information finns i [API för att hämta meddelandestatus](../data-entities/recurring-integrations.md#api-for-getting-message-status) och [Statuskontroll-API](../data-entities/data-management-api.md#status-check-api). De ER-relaterade filerna lagras i Azure blobminne som bilagor till programtabellposter så länge det behövs. En enda fil raderas från Azure blobminne tillsammans med den programtabellpost som filen var kopplad till.

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)
- [Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)
- [Konfigurera dokumenthantering](../../fin-ops/organization-administration/configure-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
