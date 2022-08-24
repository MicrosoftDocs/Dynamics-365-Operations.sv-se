---
title: Aktivera den globala valutakurstypen för källskatt och datumtypsinställningar
description: I den här artikeln förklaras hur du aktiverar den globala inställningen av valutakurstyp och datumtyp för källskatt.
author: kailiang
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 41f12a33651c14439f3a59c5c2f2d34019dada2d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229968"
---
# <a name="enable-the-global-withholding-tax-currency-exchange-rate-type-and-date-type-setup"></a>Aktivera den globala valutakurstypen för källskatt och datumtypsinställningar

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

I den här artikeln förklaras hur du aktiverar den globala inställningen av valutakurstyp och datumtyp för källskatt. Du kan nu välja en dedicerad valutakurstyp och datumtyp för valutakursberäkning för källskattevalutan. Dessa val bestämmer den valutakurs i utländsk valuta som används för att beräkna källskattebeloppet, i källskattevalutan, i betalningstransaktionerna.

Den här funktionen är tillgänglig i Microsoft Dynamics 365 Finance version 10.0.29 och senare versioner.

1. Gå till **Moms** \> **Inställningar** \> **Parametrar** \> **Allmänna redovisningsparametrar**.
2. På fliken **Källskatt** ställ in **Aktivera källskattevaluta för förskott** till **Ja**.
3. I fältet **valutakurstyp**, välj en växelkurstyp för källskattevalutan.
4. Välj en beräkningsdatumtyp i fältet **Beräkningsdatumtyp** som bestämmer valutakursen för källskatten:

    - **Betalningsdatum** – Bestäm valutakurs baserat på bokföringsdatumet för betalningsjournalen.
    - **Fakturadatum** – Bestäm valutakurs baserat på fakturadatumet för fakturajournalen. Om fakturadatumet för verifikationen är tomt används fakturabokföringsdatumet. 
    - **Dokumentdatum** – Bestäm valutakurs baserat på dokumentdatumet för betalningsjournalen. Om dokumentdatumet för verifikationen är tomt används betalningsdatumet.

5. Välj **Spara**.

Om transaktionsvalutan skiljer sig från källskattevalutan som definierats i källskattekoden beräknas beloppet i källskattevalutan från transaktionsvalutan, baserat på de föregående inställningarna, och registreras i de bokförda källskattetransaktionerna.
