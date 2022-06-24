---
title: Flytta NF-e XML-filer som bilagor
description: I den här artikeln förklaras hur du flyttar NF-e XML-filer från din Microsoft Dynamics 365 Finance- eller Dynamics 365 Supply Chain Management-databas och gör dem tillgängliga som bilagor istället.
author: gionoder
ms.date: 11/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2022-01-27
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: ce9061896759efeb8e8960e84656d5fc1f0616ae
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877909"
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
