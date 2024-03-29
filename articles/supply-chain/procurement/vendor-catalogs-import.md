---
title: Importera leverantörskataloger
description: Denna artikel beskriver hur du importerar leverantörskatalogdata.
author: GalynaFedorova
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests, CatVendorCatalogDetails, CatVendorCatalogReleaseApprovedProducts, CatVendorCMRDetails, CatVendorCatalogProductPerCompanyStatus, CatVendorMaintenanceEventLog, CatVendorCatalogReviewTool, CatVendorCatalogFileUpload, CatVendorCatalogMaintenanceRequest, CatVendorCatalogFileInLegalEntity, CatVendorCatalogSchema, CatVendorCatalogFilePreviewPane, CatVendorCatalogImportParameter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gfedorova
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 923715893b9f1c4b87d7bbb67e200f8cb8f92e6b
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015567"
---
# <a name="import-vendor-catalogs"></a>Importera leverantörskataloger

[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a>Import av leverantörskataloger

I Dynamics 365 Supply Chain Management kan inköpare skapa och underhålla kataloger som anställda i företaget kan använda när de beställer artiklar och tjänster för intern användning. Om du vill skapa en anskaffningskatalog kan du lägga till artiklar och tjänster som du vill göra tillgänglig för anställda, antingen genom att importera produktkatalogdata eller genom att manuellt lägga till produktkatalogdata till produktmallen. 

Du kan överföra katalogdata som skickas av en leverantör från Microsoft Dynamics 365-klienten.

Den produktdata som en leverantör skickar till dig i form av en CMR-fil (Catalog Maintenance Request) måste vara i XML-format. CMR-filen ska innehålla information om de produkter som leverantören tillhandahåller till ditt företag.

## <a name="import-vendor-catalog-data"></a>Importera leverantörskatalogdata

Om du vill importera leverantörskatalogdata måste du utföra följande uppgifter:

1. Ställ in ett projekt i arbetsytan Datahantering när du har definierat dina datamappningsregler. Välj **Datahantering** och markera **Konfigurera roller för dataprojekt**.

2. Ställ in en anskaffningskategorihierarki och tilldela dina leverantörer till anskaffningskategorier. Om du använder artikelkoder, lägg till artikelkoder till anskaffningskategorierna. För information om hur du konfigurerar en anskaffningskategorihierarki, se [Ställ in en anskaffningskategorihierarki](../procurement/tasks/set-up-procurement-category-hierarchy.md).

3. Konfigurera leverantören för katalogimport Markera en leverantör och välj sedan **Anskaffning** > **Ställ in** > **Konfigurera leverantör för katalogimport**.

4. Konfigurera arbetsflöde för katalogimport. Skapa en mall för CMR-fil och dela den med leverantören.

5. Välj **Anskaffning och källa** \> **Kataloger** \> **Leverantörskataloger** om du vill skapa en leverantörskatalog. CMR-filen (Catalog Maintenance Request) som du får från leverantören grupperas i katalogen.

6. Överför CMR-filen.

7. Granska, godkänn eller avvisa produkterna i leverantörskatalogen. Produkter som mappas automatiskt till anskaffningskategorier. 

Godkända produkter läggs till i produktmallen och frisläpps för de valda juridiska personer. Endast godkända produkter kan läggas till anskaffningskatalogen.

## <a name="generate-a-catalog-import-file-template"></a>Skapa mall för katalogfil för import

En filmall för katalogimport är en XSD-fil som du använder för att skapa en CMR-fil för en leverantörs produkter. Du kan använda CMR-filen om du vill skapa en ny katalog, ersätta en existerande katalog eller ändra en existerande katalog.

1. Välj **Anskaffning och källa** \> **Kataloger** \> **Leverantörskataloger** och dubbelklicka på den katalog som du ska arbeta med.

2. Hämta en aktuella katalogimportmallen (XSD-fil). På sidan **Uppdatera katalog** i **Åtgärdsfönstret** klickar du på fliken **Kataloger** i gruppen **Relaterad information** genom att klicka på **Skapa katalog** och välj **Anskaffningskategori**.

    - Med alternativet **Anskaffningskategori** kan du generera en katalogmall som innehåller anskaffningskategorierna där leverantören har behörighet att leverera produkter.

3. Välj plats där du vill lagra katalogfilmallen och spara filen i dialogrutan **Spara som**.

Mer information och exempel finns i det här blogginlägget: [leverantörskataloger i Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]