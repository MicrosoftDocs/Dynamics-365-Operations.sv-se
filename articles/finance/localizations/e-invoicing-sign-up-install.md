---
title: Registrering och installation av tjänsten för e-fakturering
description: I detta ämne finns information om hur du registrerar dig för och installerar tjänsten för e-fakturering.
author: dkalyuzh
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4ab16652e4a50dd71a5d0b2b49b4dd79e327f7a8
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371766"
---
# <a name="sign-up-for-and-install-the-electronic-invoicing-service"></a>Registrering och installation av tjänsten för e-fakturering

[!include [banner](../includes/banner.md)]

I detta ämne finns information om hur du registrerar dig för och installerar tjänsten för e-fakturering. Processen är uppdelad i fyra steg. Steg 1 till 3 är obligatoriska, medan steg 4 är valfritt.

### <a name="step-1-sign-up-for-regulatory-configuration-service"></a>Steg 1: Registrera dig för Regulatory Configuration Service

Regulatory Configuration Services (RCS) tillhandahåller den konfigurations- och designupplevelse som används för att konfigurera e-fakturering. Resurser som t.ex. miljöer och funktioner för e-fakturering skapas, underhålls och hanteras i RCS. När resurserna är klara publiceras de i tjänsten fö e-fakturering.

Mer information om RCS finns i [Regulatory Configuration Services (RCS) – globaliseringsfunktioner](rcs-globalization-feature.md).

För att registrera dig för RCS, gå till sidan [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

### <a name="step-2-install-the-add-in-for-microservices-in-microsoft-dynamics-lifecycle-services"></a>Steg 2: Installera tillägget för mikrotjänster i Microsoft Dynamics Lifecycle Services

Tjänsten för e-fakturering är en uppsättning mikrotjänster som finns i Microsofts datacenter. Dynamics 365 Finance- och Dynamics 365 Supply Chain Management-kunder har som standard inte åtkomst till e-faktureringstjänsten. Du måste installera det som ett tillägg i Microsoft Dynamics Lifecycle Services (LCS). När du installerar tillägget registreras din Ekonomi- eller Supply Chain Management-miljö i kassan för program som tillåts ansluta till e-faktureringstjänsten.

För att slutföra detta steg, se [Installera tillägget för mikrotjänster i Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md).

### <a name="step-3-set-up-rcs"></a>Steg 3: Konfigurera RCS

Du måste konfigurera integreringen mellan RCS och e-faktureringstjänsten. Du måste även ställa in huvudkomponenterna.

För att slutföra detta steg, se [Konfigurera Regulatory Configuration Service (RCS)](e-invoicing-set-up-rcs.md).

### <a name="step-4-microsoft-power-platform-plug-in-admin-reference"></a>Steg 4: Administratörsreferens för  Microsoft Power Platform-tillägg

Vissa scenarier kräver integrering med Dataverse inom ramarna för Microsoft Power Platform.

För närvarande är denna konfigurering obligatorisk om du ska använda e-faktureringslösningar för e-faktureringsscenarier för Indonesien. Det är dock valfritt för e-faktureringsscenarier för Saudiarabien. Mer information finns i [Tillgänglighet för e-faktureringsfunktioner efter land eller region](e-invoicing-country-specific-availability.md).

För att slutföra detta steg, se [Administratörsreferens för Microsoft Power Platform-tillägg](e-invoicing-power-platform-plug-in.md).
