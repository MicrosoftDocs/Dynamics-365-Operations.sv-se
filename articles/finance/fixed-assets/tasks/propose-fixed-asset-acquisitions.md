---
title: Föreslå förvärv av anläggningstillgång
description: Detta avsnitt beskriver hur du anskaffar en anläggningstillgång med hjälp av anskaffningsförslaget i anläggningstillgångsjournalen.
author: saraschi2
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d529cd53b41827a78b282afd4d2c69d2f2db555e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817182"
---
# <a name="propose-fixed-asset-acquisitions"></a>Föreslå förvärv av anläggningstillgång

[!include [banner](../../includes/banner.md)]

Detta avsnitt beskriver hur du anskaffar en anläggningstillgång med hjälp av anskaffningsförslaget i anläggningstillgångsjournalen. Här används revisorrollen och demonstrationsdata för den juridiska USMF-personen. Om du vill skaffa en anläggningstillgång via en förslagsjournal för anläggningstillgångar måste du först skapa anläggningstillgångsposten och sedan definiera anskaffningspriset i tillgångsförteckningen.

## <a name="create-an-asset-acquisition-proposal"></a>Skapa ett förslag för anläggningstillgång

Gör på följande sätt om du vill skapa ett förslag för anläggningstillgång. 

1. I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar**.
2. Välj **Ny**.
3. I fältet **Namn** anger eller väljer du ett värde.
4. Klicka på **Rader** i åtgärdsfönstret.
5. Välj **Förslag**.
6. Välj **Anskaffningsförslag**.
7. Välj **filter**. Välj **Återställ** för att rensa tidigare värden.
8. Välj raden med **numret på anläggningstillgången**.
9. I fältet **Kriterier** anger du eller väljer ett värde. Ange återstående kriterier för de anläggningstillgångar som du vill anskaffa med detta förslag.  
10. Välj **OK** två gånger för att avsluta fönstret.
- Kontrollera de skapade transaktionsraderna.  
- Endast anläggningstillgångar med anskaffningsdatum och anskaffningspris på räkenskapsboken inkluderas i anskaffningsförslaget.  
11. På sidan väljer du fliken **Böcker**.
12. Vald **bokföring**

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a>Inkludera ekonomiska standarddimensioner i ett anskaffningsförslag

Anskaffningstransaktionen kan skapas med hjälp av Excel-tillägg genom att gå till **Anläggningstillgångar > Journalposter > Anläggningstillgångsjournal**. Skapa en ny journal och flytta till området **Rader** på sidan, markera Excel-ikonen och välj sedan en journalrad för anläggningstillgångar. Systemet skapar och öppnar en Excel-mall som representerar journalrader. Du kan lägga till data för de journalrader du lägger till i mallen och sedan publicera den informationen igen i systemet. 

Om standarddimensioner har ställts in för den valda tillgångsboken och motsvarande anläggningstillgångar som angetts i Excel-mallen, anropas de ekonomiska standarddimensionerna från huvuddata i tillgångsboken när journalen publiceras från Excel i systemet. Om du vill att ekonomiska dimensioner ska inkluderas automatiskt i en tillgångsbok när du publicerar anläggningstillgångsjournalen från Excel-tillägget, måste standarddimensionerna ställas in i förväg.  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
