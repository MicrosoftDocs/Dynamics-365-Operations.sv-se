---
title: Globaliseringstjänster i Dynamics 365
description: Detta ämne ger en översikt över globaliseringstjänsterna i Microsoft Dynamics 365.
author: kfend
ms.date: 04/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
ms.openlocfilehash: eebf74ab30a544f6561cf5782148d12b58d9c4b7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278245"
---
# <a name="dynamics-365-globalization-services"></a>Globaliseringstjänster i Dynamics 365

[!include [banner](../includes/banner.md)]

Följande globaliseringstjänster kan konfigureras i syfte att utöka kapaciteten hos vissa Microsoft Dynamics 365-onlinetjänster:

- **Regulatory Configuration Service (RCS)** stöder konfigurationen av olika typer av elektroniska dokument och rapporter. RCS innehåller en förbättrad version av designern för elektronisk rapportering (ER) där konfigurationsdatabasen är en fristående tjänst. Mer information finns i [Regulatory Configuration Service](rcs-overview.md).
- Vid **e-fakturering** samlas konfigurerbara format för omvandling, digitala signaturer och konfigurerbara integreringar för anslutning till externa webbtjänster, inklusive certifiering och svarshantering. Mer information finns i [E-fakturering](e-invoicing-service-overview.md).
- **Skatteberäkning** ger ökad flexibilitet genom att stödja flera skatte-ID, bestämmande av skattekod, skatteberäkningsdesigner och en körtidsmotor för att följa komplexa skatteregler globalt. Mer information finns i [Skatteberäkning](global-tax-calcuation-service-overview.md).

Dessa globaliseringstjänster tillhandahåller direktintegration med följande onlinetjänster i Dynamics 365:

| Onlinetjänster | Lagstadgad konfigurationstjänst | E-fakturering | Skatteberäkning (förhandsversion) |
|----------------|-----|----------------------|---------------------------|
| Dynamics 365 Finance | Ja | Ja | Ja | 
| Dynamics 365 Supply Chain Management | Ja | Ja | Ja | 
| Dynamics 365 Project Operations | Ja | Ja | Inte tillämpligt | 
| Dynamics 365 Commerce | Ja | Inte tillämpligt | Inte aktuellt | 

> [!NOTE]
> På grund av skillnader i tillgängligheten för geografiska platser i Azure (geos) för RCS kan konfigurationen av den här tjänsten leda till att kunddata överförs utanför det område som valts för tillämplig Dynamics 365-onlinetjänst. Mer information finns i [Dynamics 365 och Power Platform: Tillgänglighet, dataplats, språk och lokalisering](https://aka.ms/rcs/D365Productavailabilityguide).
