--- 
title: "Skapa konfigurationsleverantörer och markera dem som aktiva"
description: "I följande steg förklaras hur en användare som är tilldelad rollen som systemadministratör eller utvecklare för elektronisk rapportering kan skapa en konfigurationsleverantör för elektronisk rapportering (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 37957f224cb57fd9f6c5014740bcea124a99a03a
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Skapa konfigurationsleverantörer och markera dem som aktiva

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg förklaras hur en användare som är tilldelad rollen som systemadministratör eller utvecklare för elektronisk rapportering kan skapa en konfigurationsleverantör för elektronisk rapportering (ER). Alla ER-konfigurationer refererar till leverantören som författare av konfigurationen. I det här exemplet ska du skapa en konfigureringsleverantör för exempelföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringsleverantörer delas mellan alla företag.


## <a name="create-a-provider"></a>Skapa en leverantör
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Klicka på konfigurationsleverantörer.
3. Klicka på Ny.
    * En leverantörspost har ett unikt namn och en unik webbadress. Granska innehållet på den här sidan och hoppa över den här proceduren om en post för Litware, Inc (`http://www.litware.com`) redan finns.  
4. Skriv "Litware, Inc." i fältet Namn.
    * Litware Inc.  
5. Skriv in `http://www.litware.com` i fältet för Internetadress.
6. Klicka på Spara.
7. Stäng sidan.

## <a name="select-as-an-active-provider"></a>Välj som en aktiv leverantör
1. Välj leverantören "Litware, Inc.".
2. Klicka på Ställ in aktiv.


