---
title: Ändra avskrivningspraxis för flera anläggningstillgångar
description: Uppgiften uppdaterar avskrivningspraxis för en viss grupp av anläggningstillgångar.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 39930134782b40de05a92a6ad51c4f628f304a78
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142902"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a>Ändra avskrivningspraxis för flera anläggningstillgångar

[!include [banner](../../includes/banner.md)]

Uppgiften uppdaterar avskrivningspraxis för en viss grupp av anläggningstillgångar. I den här uppgiftsguiden används demonstrationsföretaget USMF.

1. Gå till Anläggningstillgångar > Periodiska uppgifter > Massuppdatering
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avskrivningsbok.
3. Klicka på länken på den valda raden i listan.
4. Ange datum i fältet Satt i tjänst - start.
5. Ange datum i fältet Satt i tjänst - slut.
    * Endast tillgångar som är del av den valda avskrivningsboken och som har satts i tjänst under denna tid kommer att uppdateras.  
6. Välj alternativ i fältet Aktuell avskrivningspraxis.
    * Endast tillgångar som har aktuell avskrivningspraxis uppdateras.  
7. Välj alternativ i fältet Ny avskrivningspraxis.
    * Bekräfta att rapporten skrivs ut till valt mål.  
8. Expandera avsnittet Poster som ska ingå.
9. Klicka på Filter.
10. Välj Anläggningstillgångsgrupp i listan.
11. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kriterier.
12. Markera den valda anläggningstillgångsgruppen.
13. Klicka på länken på den valda raden i listan.
14. Klicka på OK.
15. Klicka på OK.
    *  Resultatet av processen visas på massuppdateringrapporten.     

