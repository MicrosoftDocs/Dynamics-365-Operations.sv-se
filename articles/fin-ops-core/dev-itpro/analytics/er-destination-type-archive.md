---
title: Arkivera ER-målstyp
description: Det här ämnet innehåller information om hur du konfigurerar en arkivdestination för varje MAPP- eller FIL-komponent i ett ER-format (elektronisk rapportering).
author: NickSelin
manager: AnnBe
ms.date: 11/30/2020
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
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 72b896ca692a54200ff79b14d0b5dc6ab4b0fe27
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562056"
---
# <a name="archive-er-destination-type"></a>Arkivera ER-målstyp

[!include [banner](../includes/banner.md)]

Du kan konfigurera en arkivdestination för varje **Mapp**- eller **Fil**-komponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument. Baserat på destinationsinställningen lagras ett genererat dokument som en bilaga till en post i ER-jobblistan. Visa resultaten genom att gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Arkiverade elektroniska rapporteringsjobb**.

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

> [!NOTE] 
> I ER-ramverket lagras filer permanent i Azure blobminne till skillnad från ramverket för datahantering som tillämpar den bevarande principen om sju dagar för dokument som måste bearbetas. Mer information finns i [API för att hämta meddelandestatus](../data-entities/recurring-integrations.md#api-for-getting-message-status) och [Statuskontroll-API](../data-entities/data-management-api.md#status-check-api). De ER-relaterade filerna lagras i Azure blobminne som bilagor till programtabellposter så länge det behövs. En enda fil raderas från Azure blobminne tillsammans med den programtabellpost som filen var kopplad till.

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)
- [Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)
- [Konfigurera dokumenthantering](../../fin-ops/organization-administration/configure-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]