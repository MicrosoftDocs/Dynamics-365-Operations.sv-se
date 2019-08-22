---
title: Tillgångsdokument
description: I det här avsnittet beskrivs tillgångsdokument i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1c90788da7ad536fb9978db18160ccf6c158033
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783589"
---
# <a name="asset-documents"></a>Tillgångsdokument

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

I det här avsnittet beskrivs tillgångsdokument i tillgångshantering.

I tillgångshantering kan du ställa in dokument så att de automatiskt är relaterade till jobbtyper, tillgångstillverkare, tillgångstyper eller tillgångar, till exempel. Den här funktionen är användbar när uppdaterade dokumentversioner släpps. I så fall behöver du bara placera det uppdaterade dokumentet på standardplatsen som du använder för Microsoft Dynamics 365 for Finance and Operations-dokumenten och bifoga dokumentet till den tillgångsdokumentpost som du har skapat. Det uppdaterade dokumentet kan sedan nås från menyalternativen **alla tillgångar**, **aktiva tillgångar**, **mina aktiva tillgångar**, **alla arbetsorder** och **aktiva arbetsorderjobb**. Processen för att bifoga dokument till en tillgångsdokumentpost använder hanteringssystemet för standarddokument i Finance and Operations.

**Exempel 1:** ett dokument som är relaterat till en jobbtyp kan beskriva en procedur för den jobbtypen.

**Exempel 2:** ett dokument som är relaterat till en kombination av en tillgångstyp, tillverkare och modell kan vara standardhandboken för den valda modellen för tillgångstillverkarmodell.

## <a name="create-asset-document-relation"></a>Skapa relation till tillgångsdokument

1. Välj **tillgångshantering** \> **inställningar** \> **tillgångsdokumenet**.
2. Välj **ny** om du vill skapa en tillgångsdokumentpost.
3. Beroende på hur specifik du vill att dokumentrelationen ska vara, gör du relevanta val i ett eller flera av följande fält: **tillgångstyp**, **tillverkare**, **modell**, **tillgång**, **jobbtypkategori**, **Jobbtyp**, **Jobbtypvariant** och **jobbkrav**. Alternativen som är tillgängliga i fälten **jobbtypvariant** och **jobbehov** beror på ditt val i fältet **jobbtyp**.

    > [!NOTE]
    > När systemet söker efter dokument som ska relateras till en tillgång eller en arbetsorder går tillgångshanteraren igenom alla tillgångsdokumentposter för att kontrollera om det finns en möjlig matchning. Den kontrollerar alltid den mest specifika kombinationen först. Med andra ord söker tillgångshantering först efter en matchning för fältet **jobbehov**. Om ingen matchning hittas söker den efter en matchning för fältet **jobbtypvariant** och så vidare. Om ingen matchning hittas söker den efter en matchning för fältet **jobbtyp** och så vidare. Som du kan se i layouten på sidan **tillgångsdokument** innebär detta att, för att hitta den mest specifika kombinationen, kontrollerar tillgångshantering varje post från höger till vänster för en matchning. Flera dokument kan vara relaterade till en tillgång eller en arbetsorder. Du kan redigera servicenivån på en underhållsbegäran eller en arbetsorder som du behöver.

4. Välj **bilagor**. Standardsidan **dokumenthantering** i Finance and Operations visas.
5. Ställ in de dokument eller noteringar som ska kopplas till tillgångsdokumentposten. När du bifogar dokument visar fältet **bilagor** antalet dokument som är relaterade till posten.
