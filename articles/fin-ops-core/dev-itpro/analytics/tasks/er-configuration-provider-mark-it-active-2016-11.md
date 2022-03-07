---
title: Skapa konfigurationsleverantörer och markera dem som aktiva
description: I detta avsnitt beskriver följande steg förklaras hur en användare som är tilldelad rollen som systemadministratör eller utvecklare för elektronisk rapportering kan skapa en konfigurationsleverantör.
author: NickSelin
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5b429badcbcc0e9829d82785a6e1f1a2504f5ec9b9ac74d249032f272dea103
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747257"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Skapa konfigurationsleverantörer och markera dem som aktiva

[!include [banner](../../includes/banner.md)]

I detta avsnitt beskriver följande steg förklaras hur en användare som är tilldelad rollen som systemadministratör eller utvecklare för elektronisk rapportering kan skapa en konfigurationsleverantör för elektronisk rapportering (ER). Alla ER-konfigurationer refererar till leverantören som författare av konfigurationen. I det här exemplet ska du skapa en konfigureringsleverantör för exempelföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringsleverantörer delas mellan alla företag.

## <a name="create-a-provider"></a>Skapa en leverantör
1. Gå till **navigerings fönstret** i det övre vänstra hörnet och välj **organisationsadministration**.
2. Gå till **Arbetsytor > Elektronisk rapportering**.
3. Gå till **relaterade länkar > konfigurationsleverantörer**.
4. Välj **Ny**.
    - En leverantörspost har ett unikt namn och en unik webbadress. Granska innehållet på den här sidan och hoppa över den här proceduren om en post för Litware, Inc (https://www.litware.com) redan finns.  
5. I fältet Namn skriver du `Litware, Inc.`.
6. Skriv in "`https://www.litware.com`" i fältet för Internetadress.
7. Välj **Spara**.
8. Stäng sidan.

## <a name="select-as-an-active-provider"></a>Välj som en aktiv leverantör
1. Välj leverantören "Litware, Inc.".
2. Ställ in **Ange aktiva**.

![Sidan Arbetsyta för elektronisk rapportering.](../media/GER-Task-ActiveProvider-1.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]