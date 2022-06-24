---
title: Tillgångsdokument
description: I denna artikel beskrivs tillgångsdokument i Tillgångshantering.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectDocument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a2e8d72dc938c43e266c6b7c39329f827c56607a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899481"
---
# <a name="asset-documents"></a>Tillgångsdokument

[!include [banner](../../includes/banner.md)]

 

I denna artikel beskrivs tillgångsdokument i Tillgångshantering.

I Tillgångshantering kan du konfigurera dokument så att de automatiskt är relaterade till jobbtyper, tillgångstillverkare, tillgångstyper eller tillgångar, till exempel. Den här funktionen är användbar när uppdaterade dokumentversioner släpps. I så fall behöver du bara placera det uppdaterade dokumentet på standardplatsen som du använder för Supply Chain Management-dokumenten och bifoga dokumentet till den tillgångsdokumentpost som du har skapat. Det uppdaterade dokumentet kan sedan nås från menyalternativen **alla tillgångar**, **aktiva tillgångar**, **mina aktiva tillgångar**, **alla arbetsorder** och **aktiva arbetsorderjobb**. Processen för att bifoga dokument till en tillgångsdokumentpost använder hanteringssystemet för standarddokument.

**Exempel 1:** ett dokument som är relaterat till en jobbtyp kan beskriva en procedur för den jobbtypen.

**Exempel 2:** ett dokument som är relaterat till en kombination av en tillgångstyp, tillverkare och modell kan vara standardhandboken för den valda modellen för tillgångstillverkarmodell.

## <a name="create-asset-document-relation"></a>Skapa relation till tillgångsdokument

1. Välj **Tillgångshantering** \> **inställningar** \> **tillgångsdokumenet**.
2. Välj **ny** om du vill skapa en tillgångsdokumentpost.
3. Beroende på hur specifik du vill att dokumentrelationen ska vara, gör du relevanta val i ett eller flera av följande fält: **tillgångstyp**, **tillverkare**, **modell**, **tillgång**, **jobbtypkategori**, **Jobbtyp**, **Jobbtypvariant** och **jobbkrav**. Alternativen som är tillgängliga i fälten **jobbtypvariant** och **jobbehov** beror på ditt val i fältet **jobbtyp**.

    > [!NOTE]
    > När systemet söker efter dokument som ska relateras till en tillgång eller en arbetsorder går tillgångshanteraren igenom alla tillgångsdokumentposter för att kontrollera om det finns en möjlig matchning. Den kontrollerar alltid den mest specifika kombinationen först. Med andra ord söker Tillgångshantering först efter en matchning för fältet **jobbehov**. Om ingen matchning hittas söker den efter en matchning för fältet **jobbtypvariant** och så vidare. Om ingen matchning hittas söker den efter en matchning för fältet **jobbtyp** och så vidare. Som du kan se i layouten på sidan **tillgångsdokument** innebär detta att, för att hitta den mest specifika kombinationen, kontrollerar Tillgångshantering varje post från höger till vänster för en matchning. Flera dokument kan vara relaterade till en tillgång eller en arbetsorder. Du kan redigera servicenivån på en underhållsbegäran eller en arbetsorder som du behöver.

4. Välj **bilagor**. Standardsidan **dokumenthantering** visas.
5. Ställ in de dokument eller noteringar som ska kopplas till tillgångsdokumentposten. När du bifogar dokument visar fältet **bilagor** antalet dokument som är relaterade till posten.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]