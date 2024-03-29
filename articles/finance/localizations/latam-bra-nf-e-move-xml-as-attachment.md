---
title: Flytta NF-e XML-filer som bilagor
description: I den här artikeln förklaras hur du flyttar NF-e XML-filer från din Microsoft Dynamics 365 Finance- eller Dynamics 365 Supply Chain Management-databas och gör dem tillgängliga som bilagor istället.
author: gionoder
ms.date: 11/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2022-01-27
ms.dyn365.ops.version: 10.0.25
ms.custom: 97423
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 7bb0fb975c6d73cc4e990b39ea9b5a0c0455db74
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270637"
---
# <a name="move-nf-e-xml-files-as-attachments"></a>Flytta NF-e XML-filer som bilagor

[!include [banner](../includes/banner.md)] 


När elektroniska räkenskapsdokument (NF-e) utfärdas, skapas och lagras XML-filer i Microsoft Dynamics 365 Finance- och Dynamics 365 Supply Chain Management-databaser. I lokaliseringen för Brasilien kan du använda funktionen **Flytta NF-e XML-filer som bilagor** för att fria upp det databasutrymme som dessa XML-filer förbrukar.

För ett specifikt datumintervall och ett visst skattesystem flyttar funktionen NF-e XML-filerna från din Finance- eller Supply Chain Management-databas till Blob Storage från ditt Azure-abonnemang. Med den här flytten blir filerna tillgängliga endast som bilagor. När XML-filerna har flyttats till Blob Storage tas originalfilerna bort från Finance- eller Supply Chain Management-databasen. Därför frisätts det databasutrymme som dessa filer använt.

Följ dessa steg för att aktivera funktionen **Flytta NF-e XML som bilaga**.

1. I Finance eller Supply Chain Management öppnar du arbetsytan **Funktionshantering**.
2. På fliken **Alla** söker du efter och väljer funktionen **Flytta NF-e XML som bilaga**.
3. Välj **Aktivera nu**.

Följ dessa steg när du vill flytta NF-e XML-filer som bilagor.

1. Gå till **Kundreskontra**\> **Skattedokument** \> **Elektroniska skattedokument** \> **Flytta NF-e XML som bilagor**.
2. Ange start- och slutdatum i fälten **Från datum** och **Till datum**.
3. Ange ett värde i fältet **Skattemyndighets-ID**.
4. Välj **OK**.

> [!IMPORTANT]
> Denna process går inte att ångra. När du har flyttat NF-e XML-filerna kan användarna bara visa dem genom att välja **Bilagor** högst upp på sidan **Skattedokument**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
