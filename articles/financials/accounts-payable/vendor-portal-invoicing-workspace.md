---
title: "Faktureringsarbetsyta för leverantörssamarbeten"
description: "Det här avsnittet beskriver hur du kan visa leverantörsfakturor och skicka fakturor från arbetsytan för leverantörssamarbetesfakturering."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 221534
ms.assetid: c4ed62f3-d351-41d7-a2ad-790576cde4ab
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 2368fae3913f67d9d2ce0bbe6b2e0bee7968bb15
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="vendor-collaboration-invoicing-workspace"></a>Faktureringsarbetsyta för leverantörssamarbeten

[!INCLUDE [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du kan visa leverantörsfakturor och skicka fakturor från arbetsytan för leverantörssamarbetesfakturering.

**Faktureringsarbetsyta för leverantörssamarbeten** kan användas för att visa information om leverantörsfaktura och skicka in fakturor till Microsoft Dynamics 365 for Finance and Operations med hjälp av arbetsflödesfunktionerna.


<a name="vendor-collaboration-invoicing-workspace"></a>Arbetsyta för leverantörssamarbetesfakturering
----------------------------------------

### <a name="summary-tiles"></a>Sammanfattningsrutor

**Sammanfattningsrutorna** ger en översikt över fakturorna för den valda leverantören. Du kan visa fakturor med hjälp av deras läge.
-   Utkastfakturor har inte skickats in till arbetsflödet.
-   Skickade, ej godkända fakturor är de fakturor som leverantören har skickat, men som inte har bokförts i Finance and Operations.
-   Godkända, ej betalda fakturor är de fakturor som har bokförts i Finance and Operations, men som inte ännu har betalats till fullo.
-   Betalda fakturor är de fakturor som har betalats till fullo i Finance and Operations.

Om du klickar på en ruta öppnas en filtrerad vy av listsidan **Fakturor**.

### <a name="tabular-lists"></a>Tabellistor

I avsnittet **Tabellistor** är status för faktureringen uppdelad på liknande sätt som sammanfattningsrutorna: Utkast och Skickad, ej godkända listor. En faktura kan skickas till arbetsflödet eller tas bort när den befinner sig läget Utkast. Den sista tabellistan är ett alternativ för att hitta fakturor. Du kan filtrera medan du söker för att tillåta snabbare sökningar.

### <a name="all-vendor-invoices-list-page"></a>Alla listsidor med leverantörsfakturor

Du kan visa alla bokförda och ej bokförda leverantörsfakturor på listsidan **Leverantörssamarbetesfakturor**. Du kan använda den här listsidan för att visa betalningsstatus för fakturor. Betalningsstatus omfattar Ej bokförd, Obetald, Delvis betald och Helt betald.
Skapa en ny leverantörsfaktura från en inköpsorder

Du kan skapa en ny leverantörsfaktura, genom att välja åtgärden **Ny** på **Faktureringsarbetsyta för leverantörssamarbete**. Inköpsordernumret och fakturanumret måste anges av leverantören. Som standard visas alla rader från leverantörens inköpsorder på den nya fakturan. Informationen om kvantitet och kostnad kan redigeras innan leverantörsfakturan skickas till arbetsflödet. Du kan bifoga filer, anteckningar, bilder och URL-adresser till en faktura, innan du skickar in den.

Mer information finns i [Samarbeten med externa leverantörer](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md)




